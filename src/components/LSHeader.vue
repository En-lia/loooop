<template>
    <header class="header">
        <div class="header__active-panel">
            <div class="header__menu-container">
                <LSLogo />

                <UIButtonIcon
                    class="header__menu-button"
                    @click="openMenuModal"
                >
                    <img
                        src="@/assets/images/menuIcon.svg"
                        alt="menu icon"
                    />
                </UIButtonIcon>
            </div>

            <UIInput
                placeholder="Наушники Apple..."
                class="header__search"
            >
                <template v-slot:append>
                    <img
                        src="@/assets/images/searchIcon.svg"
                        alt="search icon"
                    />
                </template>
            </UIInput>

            <LSButtonPanel class="header__button-panel" />
        </div>

        <LSNavigation class="header__navigation" />

        <Teleport to="body">
            <LSMenuModal
                v-if="isMenuModalVisible"
                @close="closeMenuModal"
            />
        </Teleport>
    </header>
</template>

<script>
import UIInput from '@/components/UI/UIInput.vue';
import UIButtonIcon from '@/components/UI/UIButtonIcon.vue';
import LSMenuModal from '@/components/LSMenuModal.vue';
import LSNavigation from '@/components/LSNavigation.vue';
import LSLogo from '@/components/LSLogo.vue';
import LSButtonPanel from '@/components/LSButtonPanel.vue';

export default {
    name: 'LSHeader',
    components: {
        LSButtonPanel,
        LSNavigation,
        LSMenuModal,
        UIInput,
        UIButtonIcon,
        LSLogo
    },
    data() {
        return {
            isMenuModalVisible: false
        };
    },
    methods: {
        openMenuModal() {
            this.isMenuModalVisible = true;
        },
        closeMenuModal() {
            this.isMenuModalVisible = false;
        }
    }
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.header {
    display: flex;
    flex-direction: column;
    padding-top: 25px;

    &__active-panel {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    &__menu-container {
        display: flex;
        justify-content: space-between;
    }

    &__search {
        min-width: 784px;
    }

    &__search-icon {
        width: 24px;
        object-position: 50% 50%;
    }

    &__menu-button {
        display: none;
    }

    @media (max-width: 1450px) {
        &__menu-button {
            display: block;
        }

        &__menu-container {
            flex-direction: row-reverse;
            gap: 10px;
        }

        &__button-panel {
            display: none;
        }

        &__navigation {
            display: none;
        }
    }

    @media (max-width: 1100px) {
        padding: 20px 20px 0 20px;

        &__search {
            width: 100%;
            min-width: auto;
        }

        &__active-panel {
            flex-direction: column;
            gap: 10px;
        }

        &__menu-container {
            width: 100%;
            flex-direction: row;
        }
    }
}
</style>
