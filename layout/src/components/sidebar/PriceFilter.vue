<template>
<div class="price">
    <h3>Цена</h3>
    <div class="price__container">
        <div class="price__low">
            <input 
                class="price__input"
                type="text" 
                v-money="moneyOptions"
                v-model="priceLow"
            >
        </div>
        <span class="price__divider"></span>
        <div class="price__high">
            <input 
                class="price__input"
                type="text" 
                v-money="moneyOptions"
                v-model="priceHigh"
            >
        </div>
    </div>
</div>
</template>

<script>
import Vue from 'vue'
import VMoney from 'v-money'
Vue.use(VMoney, {})

export default {
    data() {
        return {
            priceLow: 5500,
            priceHigh: 5500,
            moneyOptions: {
                thousands: ' ',
                suffix: ' ₽',
                precision: 0,
                masked: false
            }
        }
    }
}
</script>

<style lang="scss" scoped>
h3 {
    display: flex;
    justify-content: center;
    margin-bottom: $mid-gap;
}

.price {
    &__container {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    &__low, &__high {
        font-family: 'PT Sans';
        position: relative;
    }

    &__low::after {
        content: 'от';
        position: absolute;
        top: 10px;
        left: 8px;
        color: $color-font-secondary;
        font-size: $sm-font-size;
    }

     &__high::after {
        content: 'до';
        position: absolute;
        top: 10px;
        left: 8px;
        color: $color-font-secondary;
        font-size: $sm-font-size;
    }

    &__input {
        padding: 9px 8px 9px 26px;
        border: 1px solid $border-color;
        border-radius: 4px;
        width: 119px;
        background-color: transparent;
        outline: none;
        font-size: $md-font-size;
    }

    &__divider {
        width: 10px;
        height: 1px;
        background-color: $border-color;
    }
}
</style>