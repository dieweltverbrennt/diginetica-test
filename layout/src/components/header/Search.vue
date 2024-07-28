<template>
    <div class="search">
        <input class="search__input" :class="{'input-filled': isFilled}" type="text" placeholder="Поиск по 100 000 товаров" v-model="searchQuery">
        <div class="search__manage" v-show="isFilled">
            <button class="search__erase"
                @click="searchQuery=''"
            >
                <svg width="20" height="21" viewBox="0 0 20 21" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M20 10.5C20 16.0228 15.5228 20.5 10 20.5C4.47715 20.5 0 16.0228 0 10.5C0 4.97715 4.47715 0.5 10 0.5C15.5228 0.5 20 4.97715 20 10.5ZM13.7071 8.20711C14.0976 7.81658 14.0976 7.18342 13.7071 6.79289C13.3166 6.40237 12.6834 6.40237 12.2929 6.79289L10 9.08579L7.70711 6.79289C7.31658 6.40237 6.68342 6.40237 6.29289 6.79289C5.90237 7.18342 5.90237 7.81658 6.29289 8.20711L8.58579 10.5L6.29289 12.7929C5.90237 13.1834 5.90237 13.8166 6.29289 14.2071C6.68342 14.5976 7.31658 14.5976 7.70711 14.2071L10 11.9142L12.2929 14.2071C12.6834 14.5976 13.3166 14.5976 13.7071 14.2071C14.0976 13.8166 14.0976 13.1834 13.7071 12.7929L11.4142 10.5L13.7071 8.20711Z" fill="#A2B6C7"/>
                </svg>
            </button>
            <button class="search__find">Найти</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            searchQuery: ''
        }
    },
    computed: {
        isFilled() {
            return this.searchQuery !== '';
        }
    }
}
</script>

<style lang="scss" scoped>
.search {
    width: 100%;
    position: relative;

    &__input {
        font-family: 'Inter';
        position: relative;
        width: 100%;
        height: 48px;
        padding: 4px 16px 4px 48px;
        border: 1px solid #73AFF4;
        border-radius: 10px;
        outline: none;
        font-size: $big-font-size;
        color: #5A5A5A;
    }

    &::after {
        content: '';
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        left: 19px;
        background-image: url('@/assets/images/search.svg');
        background-repeat: no-repeat;
        background-size: 18px;
        width: 18px;
        height: 18px;
    }

    &__manage {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        right: 4px;
        display: flex;
        align-items: center;
        gap: $mini-gap;
    }

    &__erase {
        background-color: transparent;
        display: flex;
        align-items: center;
        border: none;
        outline: none;
        cursor: pointer;

        &:hover {
            path {
                fill: #0C2336;
            }
        }
    }

    &__find {
        background-color: #0BB374;
        color: #fff;
        font-weight: 600;
        font-size: $md-font-size;
        border: none;
        border-radius: 10px;
        outline: none;
        padding: 12px 24px;
        cursor: pointer;

        &:hover {
            background-color: #174DB8;
        }
    }
}

@media(max-width: 800px) {
    .search {
        &__input {
            border: none;
            padding: 0;
            border-spacing: 6px;
            border-bottom: 1px solid $border-color;
            border-radius: 0;

            &:hover, &:focus {
                border-bottom: 1px solid $color-primary;
            }
        }

        &::after {
            display: none;
        }

        &__manage {
            gap: 10px;
        }

        &__erase {
            svg {
                width: 16px;
                height: 16px;

                path {
                    fill: #CBCBCB;
                }
            }
        }

        &__find {
            background-color: $color-primary;
            font-weight: 400;
            font-size: $big-font-size;
            border-radius: 5px;
            padding: 10px 16px;
        }
    }
}
</style>