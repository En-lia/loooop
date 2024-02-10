<template>
    <div class="button-panel">
        <UIButtonIcon>
            <img
                src="@/assets/images/discoverTuneIcon.svg"
                alt="discover tune icon"
            />
        </UIButtonIcon>

        <UIButtonIcon>
            <img
                src="@/assets/images/favoriteIcon.svg"
                alt="favorite icon"
            />
        </UIButtonIcon>

        <UIButtonIcon>
            <img
                src="@/assets/images/cartIcon.svg"
                alt="cart icon"
            />
        </UIButtonIcon>
    </div>
</template>

<script>
import UIButtonIcon from '@/components/UI/UIButtonIcon.vue';

export default {
    name: 'LSButtonPanel',
    components: { UIButtonIcon }
};
</script>

<style lang="scss" scoped>
.button-panel {
    display: flex;
    gap: 45px;
}
</style>
