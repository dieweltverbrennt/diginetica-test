<template>
    <aside class="sidebar">
        <CategoryFilter />
        <PriceFilter />
        <BrandFilter />
        <SizeFilter />
    </aside>
</template>

<script>
import CategoryFilter from './CategoryFilter.vue'
import PriceFilter from './PriceFilter.vue'
import BrandFilter from './BrandFilter.vue'
import SizeFilter from './SizeFilter.vue'

export default {
    components: {
        CategoryFilter,
        PriceFilter,
        BrandFilter,
        SizeFilter
    },
    data() {
        return {
        }
    }
}
</script>

<style lang="scss">
.sidebar {
    width: 280px;
    min-width: 280px;
    display: flex;
    flex-direction: column;
    gap: 28px;

    p {
        font-size: $md-font-size;
        color: $color-font-main;
    }

    span {
        font-size: $sm-font-size;
        color: $color-font-secondary;
    }

    h3 {
        font-size: 16px;
        color: $color-font-main;
        font-weight: 600;
    }
}

@media(max-width: 800px) {
    .sidebar {
        display: none;
    }
}
</style>