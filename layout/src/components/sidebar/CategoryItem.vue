<template>
    <li class="category">
        <div 
            class="category__item" 
            :class="{'category__child': isChild, 'category__active': isActiveCategory }"
            @click="changeActiveCategory(category.id)"
        >
            <p>{{ category.name }}</p>
            <span>{{ category.count }}</span>
        </div>
        <ul class="category__children">
            <CategoryItem 
                v-for="(child, index) in category.children"
                :key="index"
                :category="child"
                :isChild="true"
                :activeCategoryId="activeCategoryId"
                @change-active-category="changeActiveCategory(child.id)"
            />
        </ul>
    </li>
</template>

<script>
import CategoryItem from './CategoryItem.vue'

export default {
    name: 'CategoryItem',
    components: {
        CategoryItem
    },
    props: {
        category: {
            type: Object,
            default: null
        },
        activeCategoryId: {
            type: Number,
            default: 0
        },
        isChild: {
            type: Boolean,
            default: false
        }
    },
    computed: {
        isActiveCategory() {
            return this.category.id === this.activeCategoryId;
        }
    },
    methods: {
        changeActiveCategory(id) {
            this.$emit('change-active-category', id)
        }
    }
}
</script>

<style lang="scss" scoped>
.category {
    &__item {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 8px 16px 8px 8px;
        border-radius: 5px;
        cursor: pointer;

        &:hover p {
            color: #7397F5;
        }
    }

    &__active {
        background-color: #E2EFFF;

        &:hover p {
            color: $color-font-main;
        }
    }

    &__active span {
        color: $color-font-main;
    }

    &__children {
        list-style-type: none;
    }

    &__child {
        padding-left: 32px;
    }
}
</style>