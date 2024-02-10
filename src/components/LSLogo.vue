<template>
    <UIButtonIcon
        class="logo"
        @click="$router.push('/')"
    >
        <img
            alt="Loooop shop logo"
            src="@/assets/images/logo.svg"
        />
    </UIButtonIcon>
</template>

<script>
import UIButtonIcon from '@/components/UI/UIButtonIcon.vue';

export default {
    name: 'UILogo',
    components: {
        UIButtonIcon
    }
};
</script>

<style scoped>
.logo {
    cursor: pointer;
}
</style>
