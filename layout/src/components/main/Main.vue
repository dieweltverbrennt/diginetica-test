<template>
<div>
    <h2>Название категории</h2>
    <main class="content">
        <ContentItem 
            v-for="(item, index) in contentData"
            :key="index"
            :item="item"
        />
    </main>
</div>
</template>

<script>
import ContentItem from './ContentItem.vue'

export default {
    components: {
        ContentItem
    },
    data() {
        return {
            contentData: [
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: false
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                },
                {
                    brand: "Бренд",
                    name: "Полное название товара в несколько строк для вида с обрывом в конце...",
                    newPrice: 5990,
                    oldPrice: 5990,
                    discount: 25,
                    isHit: true,
                    isAvailable: true
                }
            ]
        }
    }
}
</script>

<style lang="scss">
.content {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    column-gap: $big-gap;
    row-gap: $big-gap;
    font-size: 14px;
}

h2 {
    font-size: 22px;
    font-weight: 400;
    margin-bottom: 12px;
}

p {
    color: $color-font-main;
}

span {
    color: $color-font-secondary;
    line-height: 1;
}

@media(max-width: 1300px) {
    .content {
        grid-template-columns: 1fr 1fr;
    }
}

@media(min-width: 799px) {
    .content {
        column-gap: 12px;
        row-gap: $mid-gap;
    }

    h2 {
        display: none;
    }
}
</style>