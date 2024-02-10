<template>
    <UISlider class="banner">
        <SwiperSlide
            v-for="(banner, i) in banners"
            :key="i"
        >
            <img
                :alt="`banner-${n}`"
                :src="banner"
                class="banner__slide-image"
            />
        </SwiperSlide>
    </UISlider>
</template>

<script>
import UISlider from '@/components/UI/UISlider.vue';
import { SwiperSlide } from 'swiper/vue';
import banner1 from '../assets/images/banner-1.svg';
import banner2 from '../assets/images/banner-2.svg';
import banner3 from '../assets/images/banner-3.svg';
import banner4 from '../assets/images/banner-4.svg';

export default {
    name: 'LSBanner',
    components: {
        UISlider,
        SwiperSlide
    },
    data() {
        return {
            banners: [banner1, banner2, banner3, banner4]
        };
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
