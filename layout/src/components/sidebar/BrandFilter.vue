<template>
    <div class="brand">
        <div class="brand__header">
            <h3>Бренд</h3>
            <span @click="cleanFilter">Очистить</span>
        </div>

        <MiniSearch 
            :isCoincidences="isCoincidences"
            :isCleaned="isCleaned"
            @search-input="findCoincidences"
        />

        <CheckboxList 
            :list="dynamicBrandsList"
        />
    </div>
</template>

<script>
import CheckboxList from './CheckboxList.vue'
import MiniSearch from './MiniSearch.vue'

export default {
    components: {
        CheckboxList,
        MiniSearch
    },
    data() {
        return {
            brandsList: [
                {
                    name: 'Атрибут',
                    count: 3,
                    check: true
                },
                {
                    name: 'Атрибут',
                    count: 3,
                    check: false
                },
                {
                    name: 'Атрибут',
                    count: 3,
                    check: false
                },
                {
                    name: 'Атрибут',
                    count: 3,
                    check: false
                },
                {
                    name: 'Атриб',
                    count: 3,
                    check: false
                },
                {
                    name: 'Атриб',
                    count: 3,
                    check: false
                },
                {
                    name: 'Атриб',
                    count: 3,
                    check: false
                }
            ],
            dynamicBrandsList: [],
            isCleaned: false
        }
    },
    created() {
        this.dynamicBrandsList = this.brandsList;
    },
    computed: {
        isCoincidences() {
            return !!this.dynamicBrandsList.length;
        }
    },
    methods: {
        findCoincidences(query) {
            if(query) {
                this.dynamicBrandsList = this.brandsList.filter(item => item.name.toLowerCase().includes(query.toLowerCase()));
            } else {
                this.dynamicBrandsList = this.brandsList;
            }
        },
        cleanFilter() {
            this.isCleaned = true;
            this.brandsList.forEach(item => item.check = false);
            this.dynamicBrandsList = this.brandsList;
            setTimeout(() => {
                this.isCleaned = false;
            }, 100)
        }
    }
}
</script>

<style lang="scss" scoped>
.brand {
    display: flex;
    flex-direction: column;
    gap: $mid-gap;

    &__header {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;

        span {
            text-decoration: underline;
            cursor: pointer;

            &:hover {
                color: $color-font-main;
            }
        }
    }
}
</style>