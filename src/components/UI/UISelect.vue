<template>
    <div class="ui-select__wrapper">
        <label for="ui-select"> {{ label }} </label>
        <div class="ui-select__container">
            <select
                name="ui-select"
                class="ui-select"
            >
                <option
                    v-for="(option, i) in options"
                    :key="i"
                    :selected="option.selected"
                >
                    {{ option.label }}
                </option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    name: 'UISelect',
    props: {
        label: {
            type: String,
            default: ''
        },
        options: {
            type: Array,
            default: () => []
        }
    }
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.ui-select {
    width: 100%;
    -moz-appearance: none;
    -webkit-appearance: none;
    appearance: none;
    border: 1px solid $blue-deep;
    border-radius: 4px;
    background-color: $white;
    padding: 10px 6px 10px 20px;
    outline: none;
    cursor: pointer;
    font-size: 16px;

    &::-ms-expand {
        display: none;
    }

    &:focus {
        outline: none;
    }

    &__container {
        position: relative;

        &::before {
            content: '';
            position: absolute;
            top: calc(50% - 2.5px);
            right: 10px;
            transform: translateY(-50%) rotate(45deg);
            display: block;
            width: 5px;
            height: 5px;
            border-style: solid;
            border-width: 2px;
            border-color: transparent $black-deep $black-deep transparent;
            pointer-events: none;
        }
    }

    &__wrapper {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 20px;
    }

    @media (max-width: 1100px) {
        &__wrapper {
            flex-direction: column;
            align-items: start;
            gap: 16px;
        }
    }
}
</style>
