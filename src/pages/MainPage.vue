<template>
    <main class="main-page">
        <LSBanner class="main-page__banner" />
        <LSCategories class="main-page__categories" />
        <LSInfoBlock class="main-page__info-block" />
    </main>
</template>

<script>
import LSBanner from '@/components/LSBanner.vue';
import LSCategories from '@/components/LSCategories.vue';
import LSInfoBlock from '@/components/LSInfoBlock.vue';

export default {
    name: 'MainPage',
    components: { LSInfoBlock, LSCategories, LSBanner }
};
</script>

<style lang="scss" scoped>
.main-page {
    &__banner {
        margin-top: 16px;
    }

    &__categories {
        margin-top: 80px;
    }

    &__info-block {
        margin-top: 135px;
    }

    @media (max-width: 1100px) {
        &__categories {
            margin-top: 25px;
        }

        &__info-block {
            margin-top: 65px;
        }
    }
}
</style>
