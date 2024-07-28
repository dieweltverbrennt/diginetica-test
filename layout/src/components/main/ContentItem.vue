<template>
    <div class="card" :class="{'card__unavailable': !item.isAvailable}">
        <div class="card__frame">
            <div class="card__hit" v-if="item.isHit">
                <p>Хит продаж</p>
                <img src="@/assets/images/hit.svg" alt="Хит продаж">
            </div>
            <img class="card__image" src="@/assets/images/card-image.svg" alt="Изображение карточки">
            <span class="card__discount">{{ item.discount }}%</span>
        </div>

        <div class="card__description">
            <span>{{ item.brand }}</span>
            <p>{{ item.name }}</p>
        </div>

        <div v-if="item.isAvailable" class="card__price">
            <p class="card__new-price">{{ formatPrice(item.newPrice) }} ₽</p>
            <span class="card__old-price">{{ formatPrice(item.newPrice) }} ₽</span>
        </div>

        <div class="card__button">
            <button v-if="item.isAvailable">Купить</button>
            <button class="card__unavailable-btn" v-else>Сообщить о поступлении</button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        item: {
            type: Object,
            default: null
        }
    },
    data() {
        return {
        }
    },
    methods: {
        formatPrice(price) {
            return price.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ' ');
        }
    }
}
</script>

<style lang="scss" scoped>
.card {
    display: flex;
    flex-direction: column;
    gap: 16px;
    cursor: pointer;

    &__frame {
        width: 100%;
        height: 200px;
        background-color: #F8F8FA;
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
    }

    &__hit {
        position: absolute;
        top: 12px;
        left: 12px;
        width: 112px;
        height: 32px;
        background-color: #FFF;
        border: 1px solid #F2F2F2;
        border-radius: 4px;
        padding: 0 8px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        color: $color-font-main;
    }

    &__discount {
        position: absolute;
        bottom: 12px;
        left: 12px;
        width: 48px;
        height: 26px;
        background-color: $color-primary;
        border-radius: 4px;
        padding: 6px 10px;
        color: #FFF;
        font-weight: 700;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    &__description {
        display: flex;
        flex-direction: column;
        gap: $mini-gap;

        p {
            line-height: 1.1;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }
    }

    &__price {
        display: flex;
        align-items: center;
        gap: $mini-gap;
    }

    &__new-price {
        font-size: $big-font-size;
        font-weight: 700;
        line-height: 0.875;
    }

    &__old-price {
        font-size: $sm-font-size;
        text-decoration: line-through;
    }

    &__button {

        button {
            font-family: 'PT Sans';
            background-color: transparent;
            border: 1px solid $color-primary;
            border-radius: 4px;
            padding: 10px 16px;
            color: $color-primary;
            font-weight: 700;
            cursor: pointer;

            &:hover {
                background-color: $color-primary;
                color: #FFF;
            }
        }

        .card__unavailable-btn {
            width: 100%;
            border: 1px solid $color-font-secondary;
            color: $color-font-secondary;
            margin-top: 46px;

            &:hover {
                background-color: $color-primary;
                color: #FFF;
                border-color: $color-font-secondary;
            }
        }
    }

    &:hover {
        .card {
            &__image {
                transform: scale(1.25);
            }

            &__description p {
                color: #125BAE;
            }
        }
    }

    &__unavailable {
        .card {
            &__frame {
                background-color: rgba(248, 248, 250, 0.5);
            }

            &__image {
                opacity: 0.5;
            }
        }

        &:hover {
            .card__image {
                transform: none;
            }

            .card__description p {
                color: $color-font-main;
            }
        }
    }
}
</style>