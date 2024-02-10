<template>
    <Swiper
        :autoplay="true"
        :modules="modules"
        :pagination="true"
        :navigation="{
            prevEl: prevButton,
            nextEl: nextButton
        }"
        class="ui-slider"
        :style="sliderStyle"
    >
        <slot></slot>

        <div
            ref="prevButton"
            class="ui-slider__button ui-slider__button-prev"
        >
            <img
                src="@/assets/images/prevArrowIcon.svg"
                alt="prevArrowIcon"
            />
        </div>

        <div
            ref="nextButton"
            class="ui-slider__button ui-slider__button-next"
        >
            <img
                src="@/assets/images/nextArrowIcon.svg"
                alt="nextArrowIcon"
            />
        </div>
    </Swiper>
</template>

<script>
import { ref } from 'vue';
import { Swiper } from 'swiper/vue';
import { Navigation, Pagination, Autoplay } from 'swiper/modules';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

export default {
    components: {
        Swiper
    },
    setup() {
        const prevButton = ref(null);
        const nextButton = ref(null);

        const sliderStyle = {
            '--swiper-pagination-color': '#94deb2',
            '--swiper-pagination-bullet-inactive-color': '#f5f5f5',
            '--swiper-pagination-bullet-inactive-opacity': '1',
            '--swiper-pagination-bullet-size': '12px',
            '--swiper-pagination-bullet-horizontal-gap': '10px',
            '--swiper-theme-color': '#000000'
        };

        return {
            modules: [Navigation, Pagination, Autoplay],
            sliderStyle,
            prevButton,
            nextButton
        };
    }
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.ui-slider {
    padding-bottom: 45px;
    border-radius: 10px;

    &__button {
        position: absolute;
        display: flex;
        align-items: center;
        justify-content: center;
        top: calc(var(--swiper-navigation-top-offset, 50%) - 33px);
        margin-top: calc(0px - (var(--swiper-navigation-size) / 2));
        width: 61px;
        height: 61px;
        z-index: 10;
        background-color: $gray-light;
        opacity: 0.8;
        border-radius: 61px;
        cursor: pointer;

        &.swiper-button-disabled {
            opacity: 0.35;
            cursor: auto;
            pointer-events: none;
        }
    }

    &__button-prev,
    .swiper-rtl .ui-slider__button-next {
        left: var(--swiper-navigation-sides-offset, 32px);
        right: auto;
    }

    &__button-next,
    .swiper-rtl .ui-slider__button-prev {
        right: var(--swiper-navigation-sides-offset, 32px);
        left: auto;
    }
}

@media (max-width: 1100px) {
    .ui-slider {
        padding-bottom: 30px;

        &__button {
            display: none;
        }
    }
}
</style>
