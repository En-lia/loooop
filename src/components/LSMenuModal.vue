<template>
    <div class="menu-modal">
        <div class="menu-modal__header">
            <LSLogo />

            <UIButtonIcon
                class="menu-modal__close-button"
                @click="closeMenuModal"
            >
                <img
                    src="@/assets/images/closeIcon.svg"
                    alt="close icon"
                />
            </UIButtonIcon>
        </div>

        <LSNavigation menuNavigation />

        <div class="menu-modal__footer">
            <LSButtonPanel />
        </div>
    </div>
</template>

<script>
import LSNavigation from '@/components/LSNavigation.vue';
import LSLogo from '@/components/LSLogo.vue';
import UIButtonIcon from '@/components/UI/UIButtonIcon.vue';
import LSButtonPanel from '@/components/LSButtonPanel.vue';

export default {
    name: 'LSMenuModal',
    components: { LSButtonPanel, LSNavigation, LSLogo, UIButtonIcon },
    methods: {
        closeMenuModal() {
            document.body.classList.remove('disable-scroll');
            this.$emit('close');
        }
    },
    mounted() {
        document.body.classList.add('disable-scroll');
    }
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.menu-modal {
    position: absolute;
    background-color: $white;
    z-index: 100;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 20px;

    &__header {
        display: flex;
        justify-content: space-between;
        margin-bottom: 22px;
    }

    &__footer {
        margin-top: 75px;
    }
}
</style>
