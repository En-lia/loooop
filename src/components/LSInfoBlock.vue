<template>
    <section class="info-block">
        <h2>Почему нас выбирают</h2>
        <div class="info-block__container">
            <div class="info-block__item info-block__guarantee">
                <img
                    src="@/assets/images/garantyIcon.svg"
                    alt="guarantee icon"
                    class="info-block__item-icon"
                />
                <div>Гарантия 5 лет</div>
            </div>
            <div class="info-block__item info-block__delivery">
                <img
                    src="@/assets/images/bicycleIcon.svg"
                    alt="bicycle icon"
                    class="info-block__item-icon"
                />
                <div>Удобаня доставка</div>
            </div>
            <div class="info-block__item info-block__price">
                <img
                    src="@/assets/images/rubleIcon.svg"
                    alt="ruble icon"
                    class="info-block__item-icon"
                />
                <div>Низкие цены</div>
            </div>

            <div class="info-block__image">
                <img
                    alt="info block image"
                    src="@/assets/images/info-block.svg"
                />
            </div>
            <div class="info-block__description">
                <div>
                    Стереосистемы - то есть, системы, собранные на базе пары
                    громкоговорителей, предназначены в первую очередь для
                    прослушивания музыки, а не для просмотра фильмов.
                </div>
                <div class="info-block__description-recommendations">
                    При выборе стереосистемы следует определиться с источником
                    сигнала: возможно, это будет сетевой или медиаплеер, CD
                    проигрыватель, радиотюнер, виниловый проигрыватель - или
                    даже все эти компоненты сразу. Здесь вы должны исходить
                    исключительно.
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'LSInfoBlock'
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.info-block {
    color: $black;
    font-weight: 500;

    &__container {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-areas:
            'guarantee img description'
            'bicycle img description'
            'ruble img description';
        gap: 20px;
        margin-top: 45px;
    }

    &__item {
        background-color: $blue;
        border-radius: 10px;
        font-size: 24px;
        padding: 34px 0 42px 0;
        text-align: center;
    }

    &__guarantee {
        grid-area: guarantee;
    }

    &__delivery {
        grid-area: bicycle;
    }

    &__price {
        grid-area: ruble;
    }

    &__image {
        grid-area: img;
    }

    &__description {
        background-color: $blue;
        border-radius: 10px;
        grid-area: description;
        padding: 48px;
        font-size: 18px;
        line-height: 32px;
    }

    &__description-recommendations {
        color: $gray-dark;
        font-weight: 400;
        margin-top: 20px;
    }

    &__item-icon {
        width: 48px;
    }

    @media (max-width: 1450px) {
        &__container {
            grid-template-columns: 1fr 1fr;
            grid-template-areas:
                'guarantee img'
                'bicycle img'
                'ruble img'
                'description description';
            gap: 20px;
            margin-top: 30px;
        }

        &__item {
            font-size: 18px;
        }

        &__description {
            font-size: 16px;
        }

        &__image img {
            width: 100%;
        }
    }

    @media (max-width: 1100px) {
        padding: 0 20px;
    }

    @media (max-width: 460px) {
        padding: 0;
        &__container {
            grid-template-columns: 1fr;
            grid-template-areas:
                'img'
                'guarantee'
                'bicycle'
                'ruble'
                'description';
            gap: 0;
        }

        &__item {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 26px;
            padding: 15px 0;
            border-radius: 0;
        }

        &__image {
            background-color: $blue;
        }

        &__description {
            border-radius: 0;
            padding: 20px;
        }
    }
}
</style>
