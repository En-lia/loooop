<template>
    <nav
        class="navigation"
        :class="{
            'navigation_theme-mobile': menuNavigation,
            'navigation_theme-desktop': !menuNavigation
        }"
    >
        <ul
            class="navigation__list"
            :class="{
                'navigation__list_theme-mobile': menuNavigation,
                'navigation__list_theme-desktop': !menuNavigation
            }"
        >
            <li
                v-for="(nav, i) in navigation"
                :key="i"
                class="navigation__item"
            >
                <a href="#">{{ nav }}</a>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    name: 'LSNavigation',
    props: {
        menuNavigation: {
            type: Boolean,
            default: false
        }
    },
    data() {
        return {
            navigation: [
                'Наушники и аудио',
                'Микрофоны и проаудио',
                'Гарнитуры',
                'Акустика',
                'Аксесуары',
                'Бренды',
                'Акции',
                'Контакты'
            ]
        };
    }
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.navigation {
    &__item {
        list-style-type: none;
    }

    &__list {
        display: flex;
        justify-content: space-between;
    }

    &_theme-desktop {
        border-radius: 10px;
        background-color: $black;
        color: $gray-light;
        padding: 15px 60px;
        margin-top: 25px;
    }

    &__list_theme-desktop {
        gap: 70px;
    }

    &_theme-mobile {
        color: $black;
        background-color: $transparent;
        padding: 0;
    }

    &__list_theme-mobile {
        color: $black;
        flex-direction: column;
        gap: 24px;
    }
}
</style>
