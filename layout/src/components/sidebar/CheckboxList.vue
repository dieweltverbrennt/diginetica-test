<template>
    <div class="checkbox__list">
        <SideListItem 
            v-for="(item, index) in list"
            :key="index"
            :item="item"
            :index="index"
        />
    </div>
</template>

<script>
import SideListItem from './SideListItem.vue'

export default {
    components: {
        SideListItem
    },
    props: {
        list: {
            type: Array,
            default: () => []
        }
    }
}
</script>

<style lang="scss" scoped>
.checkbox__list {
    display: flex;
    flex-direction: column;
    gap: 12px;
    height: 180px;
    overflow-y: scroll;

    &::-webkit-scrollbar {
        width: 3px;
    }

    &::-webkit-scrollbar-thumb {
        background-color: #CBCBCB;
        border-radius: 10px; 
    }
}
</style>