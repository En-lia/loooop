<template>
    <div class="ui-input">
        <div
            class="ui-input__wrapper"
            :class="{ 'ui-input__wrapper_focused': isFocused }"
        >
            <input
                :value="modelValue"
                @input="inputInputHandler"
                @blur="inputBlurHandler"
                @focus="inputFocusHandler"
                v-bind="$attrs"
                class="ui-input__field"
            />

            <slot name="append"></slot>
        </div>
    </div>
</template>

<script>
export default {
    name: 'UIInput',
    data() {
        return {
            isFocused: false
        };
    },
    props: {
        modelValue: [String, Number]
    },
    methods: {
        inputInputHandler(e) {
            this.$emit('update:modelValue', e.target.value);
        },
        inputFocusHandler(e) {
            this.isFocused = true;
            this.$emit('focus', e);
        },
        inputBlurHandler(e) {
            this.isFocused = false;
            this.$emit('blur', e);
        }
    }
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.ui-input {
    &__wrapper {
        display: flex;
        width: 100%;
        border: 1px solid #dcdcdc;
        border-radius: 10px;
        padding: 10px 12px 10px 16px;

        &_focused {
            border-color: $green;
            box-shadow: 0 0 14px 0 $green-light;
        }
    }

    &__field {
        width: 100%;
        min-width: 1px;
        margin: 0;
        font-family: inherit;
        font-size: 14px;
        border: none;
        outline: none;
        background-color: transparent;

        &::placeholder {
            color: #a1a1a1;
        }
    }

    &__append-icon {
        width: 24px;
        object-position: 50% 50%;
        margin-left: 5px;
    }
}
</style>
