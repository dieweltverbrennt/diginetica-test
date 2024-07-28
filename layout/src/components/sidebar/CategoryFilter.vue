<template>
    <ul>
        <CategoryItem 
            v-for="(category, index) in categoriesList" 
            :key="index" 
            :category="category"
            :activeCategoryId="activeCategoryId"
            @change-active-category="changeActiveCategory"
        />
    </ul>
</template>

<script>
import CategoryItem from './CategoryItem.vue'

export default {
    components: {
        CategoryItem
    },
    data() {
        return {
            activeCategoryId: 4,
            categoriesList: [
                {
                    id: 1,
                    name: "Название категории",
                    count: 3,
                    children: [
                        {
                            id: 2,
                            name: "Название категории",
                            count: 3
                        },
                        {
                            id: 3,
                            name: "Название категории",
                            count: 3
                        },
                        {
                            id: 4,
                            name: "Название категории",
                            count: 3
                        }
                    ]
                }
            ]
        }
    },
    methods: {
        changeActiveCategory(id) {
            this.activeCategoryId = id;
        }
    }
}
</script>

<style lang="scss" scoped>
ul {
    list-style-type: none;
    padding: none;
}
</style>