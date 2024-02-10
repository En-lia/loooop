<template>
    <button
        class="ui-button"
        :class="{ 'ui-button_active': active, 'ui-button_disabled': disabled }"
    >
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: 'UIButton',
    props: {
        disabled: {
            type: Boolean,
            default: false
        },
        active: {
            type: Boolean,
            default: false
        }
    }
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.ui-button {
    border-radius: 4px;
    border: none;
    background-color: $blue;
    cursor: pointer;
    font-size: 16px;
    padding: 10px 28px;

    &_active {
        border: 1px solid $blue-deep;
        background-color: $white;
    }
}
</style>
