<template>
    <div class="layout">
        <div class="layout__wrapper">
            <LSHeader />
            <router-view></router-view>
        </div>
    </div>
</template>

<script>
import LSHeader from '@/components/LSHeader.vue';

export default {
    name: 'LSLayout',
    components: { LSHeader }
};
</script>

<style lang="scss" scoped>
.layout {
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;

    &__wrapper {
        max-width: 1400px;
        padding-bottom: 102px;
    }

    @media (max-width: 1450px) {
        &__wrapper {
            max-width: 1050px;
        }
    }

    @media (max-width: 1100px) {
        &__wrapper {
            width: 100%;
            padding-bottom: 65px;
        }
    }
}
</style>
