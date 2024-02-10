<template>
    <section class="categories">
        <h2 class="categories__title">Категории</h2>
        <div class="categories__panel">
            <div class="categories__buttons-wrapper">
                <div class="categories__buttons">
                    <UIButton active> Все категории </UIButton>
                    <UIButton> Микрофоны </UIButton>
                    <UIButton> Акустика </UIButton>
                    <UIButton> Наушники </UIButton>
                </div>
            </div>

            <UISelect
                :options="sortOptions"
                label="Сортировать"
                class="categories__sort"
            />
        </div>
        <div class="categories__container">
            <LSCard
                v-for="(card, i) in cards"
                :key="i"
                :cardData="card"
            />
        </div>
    </section>
</template>

<script>
import UIButton from '@/components/UI/UIButton.vue';
import UISelect from '@/components/UI/UISelect.vue';
import LSCard from '@/components/LSCard.vue';
import product1 from '../assets/images/product-1.svg';
import product2 from '../assets/images/product-2.svg';
import product3 from '../assets/images/product-3.svg';
import product4 from '../assets/images/product-4.svg';
import product5 from '../assets/images/product-5.svg';
import product6 from '../assets/images/product-6.svg';
import product7 from '../assets/images/product-7.svg';
import product8 from '../assets/images/product-8.svg';

export default {
    name: 'LSCategories',
    components: { LSCard, UISelect, UIButton },
    data() {
        return {
            cards: [
                {
                    description:
                        'Микрофон “СОЮЗ Malfa”, производства фирмы Октава',
                    imgUrl: product1,
                    price: '265 900₽',
                    status: 'new'
                },
                {
                    description: 'Акустическая система Magnat Transpuls 800A',
                    imgUrl: product2,
                    price: '62 070₽',
                    status: null
                },
                {
                    description:
                        'Микрофон “СОЮЗ Boomblet”, производства фирмы Октава',
                    imgUrl: product3,
                    price: '72 100₽',
                    status: 'new'
                },
                {
                    description: 'Наушники CCA C10 Black With mic',
                    imgUrl: product4,
                    price: '125 300₽',
                    status: 'new'
                },
                {
                    description: 'Наушники Edifier HECATE G5BT black',
                    imgUrl: product5,
                    price: '11 900₽',
                    status: null
                },
                {
                    description: 'Микрофон "Lewitt LCT540SUBZERO"',
                    imgUrl: product6,
                    price: '25 170₽',
                    status: null
                },
                {
                    description: 'Полочная акустика Klipsch RP-500M II walnut',
                    imgUrl: product7,
                    price: '1 100₽',
                    status: null
                },
                {
                    description: 'RODE XCM-50 usb',
                    imgUrl: product8,
                    price: '13 455₽',
                    status: 'new'
                }
            ],
            sortOptions: [
                {
                    label: 'по популярности',
                    selected: true
                },
                {
                    label: 'по возрастанию цены',
                    selected: false
                },
                {
                    label: 'по убыванию цены',
                    selected: false
                }
            ]
        };
    }
};
</script>

<style lang="scss">
@import '@/styles/variables.scss';

.categories {
    &__panel {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        gap: 40px;
        margin-top: 45px;
        color: $black-deep;
    }

    &__buttons {
        display: flex;
        gap: 24px;
    }

    &__sort {
        & .ui-select__container {
            min-width: 330px;
        }
    }

    &__container {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
        gap: 40px 20px;
        margin-top: 40px;
    }

    @media (max-width: 1100px) {
        &__title,
        &__container,
        &__panel {
            padding: 0 20px;
        }

        &__panel {
            margin-top: 30px;
        }
    }

    @media (max-width: 460px) {
        &__container {
            padding: 0;
            gap: 0;
        }

        &__buttons {
            min-width: 620px;
            max-height: 41px;
            position: relative;
            gap: 16px;
        }

        &__buttons-wrapper {
            overflow: overlay;

            &::-webkit-scrollbar {
                width: 0;
            }
        }

        &__sort {
            & .ui-select__container {
                min-width: auto;
            }
        }
    }
}
</style>
