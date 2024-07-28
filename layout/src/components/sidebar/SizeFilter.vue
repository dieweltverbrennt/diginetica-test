<template>
    <div class="size">
        <h3>Размер</h3>
        <CheckboxList 
            :list="sizeList"
        />
    </div>
</template>

<script>
import CheckboxList from './CheckboxList.vue'

export default {
    components: {
        CheckboxList
    },
    data() {
        return {
            sizeList: [
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
                }
            ]
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
</style>