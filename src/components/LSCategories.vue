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
export default {
    name: 'LSCategories',
    components: { LSCard, UISelect, UIButton },
    data() {
        return {
            cards: [
                {
                    description:
                        'Микрофон “СОЮЗ Malfa”, производства фирмы Октава',
                    imgUrl: 'src/assets/images/product-1.svg',
                    price: '265 900₽',
                    status: 'new'
                },
                {
                    description: 'Акустическая система Magnat Transpuls 800A',
                    imgUrl: 'src/assets/images/product-2.svg',
                    price: '62 070₽',
                    status: null
                },
                {
                    description:
                        'Микрофон “СОЮЗ Boomblet”, производства фирмы Октава',
                    imgUrl: 'src/assets/images/product-3.svg',
                    price: '72 100₽',
                    status: 'new'
                },
                {
                    description: 'Наушники CCA C10 Black With mic',
                    imgUrl: 'src/assets/images/product-4.svg',
                    price: '125 300₽',
                    status: 'new'
                },
                {
                    description: 'Наушники Edifier HECATE G5BT black',
                    imgUrl: 'src/assets/images/product-5.svg',
                    price: '11 900₽',
                    status: null
                },
                {
                    description: 'Микрофон "Lewitt LCT540SUBZERO"',
                    imgUrl: 'src/assets/images/product-6.svg',
                    price: '25 170₽',
                    status: null
                },
                {
                    description: 'Полочная акустика Klipsch RP-500M II walnut',
                    imgUrl: 'src/assets/images/product-7.svg',
                    price: '1 100₽',
                    status: null
                },
                {
                    description: 'RODE XCM-50 usb',
                    imgUrl: 'src/assets/images/product-8.svg',
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
.categories {
    &__panel {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        gap: 40px;
        margin-top: 45px;
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
