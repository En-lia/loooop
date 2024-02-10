<template>
    <button class="ui-button-icon">
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: 'UIButtonIcon'
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.ui-button-icon {
    border: none;
    background-color: $transparent;
    cursor: pointer;
}
</style>
