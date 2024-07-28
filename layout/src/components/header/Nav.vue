<template>
    <nav class="nav">
        <a class="nav__item" href="#">Информация о компании</a>
        <a class="nav__item" href="#">Контакты</a>
        <a class="nav__item" href="#">Полезные ссылки</a>
    </nav>
</template>

<style lang="scss" scoped>
.nav {
    display: flex;
    flex-wrap: nowrap;
    align-items: center;
    gap: 20px;

    &__item {
        font-size: $md-font-size;
        padding: 0;
        width: max-content;
        text-decoration: none;
        color: #393939;
    }
}

@media(max-width: 1300px) {
    .nav {
        display: none;
    }
}
</style>