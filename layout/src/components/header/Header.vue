<template>
    <header class="header">
        <Info />
        <img src="@/assets/images/arrow.svg" alt="">
        <Search />
        <Nav />
    </header>
</template>

<script>
import Info from './Info.vue'
import Search from './Search.vue'
import Nav from './Nav.vue'

export default {
    components: {
        Info,
        Search,
        Nav
    }
}
</script>

<style lang="scss" scoped>
header {
    font-family: 'Inter';
    width: calc(100% - 200px);
    margin: 0 100px;
    display: flex;
    gap: $big-gap;
    padding: 12px 0;
}

img {
    cursor: pointer;
}

@media(min-width: 799px) {
    img {
        display: none;
    }
}

@media(max-width: 1300px) {
    header {
        width: calc(100% - 32px);
        margin: 0 16px;
    }
}

@media(max-width: 800px) {
    header {
        gap: $mid-gap;
        padding: 8px 0 0;
    }
}
</style>