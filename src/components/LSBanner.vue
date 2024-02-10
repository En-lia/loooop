<template>
    <UISlider class="banner">
        <SwiperSlide
            v-for="n in 4"
            :key="n"
        >
            <img
                :alt="`banner-${n}`"
                :src="`src/assets/images/banner-${n}.svg`"
                class="banner__slide-image"
            />
        </SwiperSlide>
    </UISlider>
</template>

<script>
import UISlider from '@/components/UI/UISlider.vue';
import { SwiperSlide } from 'swiper/vue';

export default {
    name: 'LSBanner',
    components: {
        UISlider,
        SwiperSlide
    }
};
</script>

<style lang="scss" scoped>
.banner {
    &__slide-image {
        width: 100%;
    }

    @media (max-width: 1100px) {
        margin: 0 20px;
    }

    @media (max-width: 460px) {
        margin: 0;

        &__slide-image {
            width: auto;
            height: 160px;
            object-fit: cover;
            max-width: 100%;
            max-height: 100%;
        }
    }
}
</style>
