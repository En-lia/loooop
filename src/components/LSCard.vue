<template>
    <div class="card">
        <span
            v-if="isNew"
            class="card__status-new"
        >
            New
        </span>

        <div class="card__image">
            <img
                alt="Product image"
                :src="cardData?.imgUrl"
            />
        </div>

        <div class="card__description">
            {{ cardData?.description }}
        </div>

        <div class="card__footer">
            <div class="card__price">{{ cardData?.price }}</div>
            <UIButtonIcon class="card__cart-button">
                <img
                    src="@/assets/images/cartIcon.svg"
                    alt="cartIcon"
                    class="card__cart-icon"
                />
            </UIButtonIcon>
        </div>
    </div>
</template>

<script>
import UIButtonIcon from '@/components/UI/UIButtonIcon.vue';
export default {
    name: 'LSCard',
    components: { UIButtonIcon },
    props: {
        cardData: {
            type: Object,
            default: () => ({})
        }
    },
    computed: {
        isNew() {
            return this.cardData?.status === 'new';
        }
    }
};
</script>

<style lang="scss" scoped>
@import '@/styles/variables.scss';

.card {
    display: flex;
    flex-direction: column;
    border: 1px solid $gray;
    border-radius: 10px;
    padding: 37px 29px 32px 35px;
    transition: box-shadow 200ms ease-in;
    cursor: pointer;

    &:hover {
        border: none;
        box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.25);

        & .card__cart-button {
            background-color: $green;
        }
    }

    &__status-new {
        position: absolute;
        background-color: $green-light;
        padding: 6px 21px;
        border-radius: 4px;
    }

    &__image {
        display: flex;
        justify-content: center;
        margin-bottom: 25px;
    }

    &__description {
        min-height: 38px;
        overflow: hidden;
        text-overflow: ellipsis;
        display: -moz-box;
        -moz-box-orient: vertical;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        line-clamp: 2;
    }

    &__price {
        font-size: 24px;
        font-weight: 600;
    }

    &__footer {
        display: flex;
        justify-content: space-between;
        margin-top: 25px;
    }

    &__cart-button {
        background-color: $black;
        border-radius: 5px;
        padding: 7px 23px;
    }

    &__cart-icon {
        width: 24px;
        filter: invert(100%) saturate(0%) brightness(120%);
    }

    @media (max-width: 460px) {
        border-radius: 0;

        &:hover {
            border: 1px solid $gray;
            box-shadow: none;
            transition: none;
        }
    }
}
</style>
