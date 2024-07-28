<template>
    <div>
        <div class="mini-search">
            <input 
                type="text" 
                placeholder="Поиск" 
                v-model="query"
                @input="findCoincidences"
            >
            <button class="mini-search__erase" 
                v-if="isFilled"
                @click="query=''"
            >
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <g opacity="0.3">
                        <path fill-rule="evenodd" clip-rule="evenodd" d="M14.6667 8.00001C14.6667 11.6819 11.6819 14.6667 8.00004 14.6667C4.31814 14.6667 1.33337 11.6819 1.33337 8.00001C1.33337 4.31811 4.31814 1.33334 8.00004 1.33334C11.6819 1.33334 14.6667 4.31811 14.6667 8.00001ZM10.4714 6.47141C10.7318 6.21107 10.7318 5.78896 10.4714 5.52861C10.2111 5.26826 9.78899 5.26826 9.52864 5.52861L8.00004 7.0572L6.47145 5.52861C6.2111 5.26826 5.78899 5.26826 5.52864 5.52861C5.26829 5.78896 5.26829 6.21107 5.52864 6.47141L7.05723 8.00001L5.52864 9.52861C5.26829 9.78895 5.26829 10.2111 5.52864 10.4714C5.78899 10.7318 6.2111 10.7318 6.47145 10.4714L8.00004 8.94282L9.52864 10.4714C9.78899 10.7318 10.2111 10.7318 10.4714 10.4714C10.7318 10.2111 10.7318 9.78895 10.4714 9.52861L8.94285 8.00001L10.4714 6.47141Z" fill="#333333"/>
                    </g>
                </svg>
            </button>
        </div>
        
        <div class="mini-search__warn" v-if="!isCoincidences">
            По вашему запросу ничего не найдено
        </div>
    </div>
</template>

<script>
export default {
    props: {
        isCoincidences: {
            type: Boolean,
            default: true
        },
        isCleaned: {
            type: Boolean,
            default: false
        }
    },
    data() {
        return {
            query: ''
        }
    },
    watch: {
        isCleaned() {
            if(this.isCleaned) {
                this.query = '';
            }
        }
    },
    computed: {
        isFilled() {
            return this.query !== '';
        }
    },
    methods: {
        findCoincidences() {
            this.$emit('search-input', this.query);
        }
    }
}
</script>

<style lang="scss" scoped>
.mini-search {
        position: relative;

        input {
            width: 100%;
            border: 1px solid $border-color;
            border-radius: 4px;
            padding: 9px 12px 9px 36px;
            outline: none;
            position: relative;
            color: $color-font-secondary;
            font-family: 'PT Sans';

            &:hover, &:focus {
                color: $color-font-main;
                border-color: #7397F5;
            }
        }

        &::after {
            content: '';
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            left: 12px;
            background-image: url('@/assets/images/mini-search.svg');
            background-repeat: no-repeat;
            background-size: 16px;
            width: 16px;
            height: 16px;
        }

        &__warn {
            margin-top: 8px;
            font-size: $md-font-size;
            color: $color-font-main;
        }

        &__erase {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            right: 12px;
            background-color: transparent;
            border: none;
            display: flex;
            align-items: center;
            cursor: pointer;

            &:hover {
                svg g {
                    opacity: 1;
                }
            }
        }
    }
</style>