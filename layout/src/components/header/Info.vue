<template>
    <div class="info">
        <div class="info__logo">
            <img src="@/assets/images/logo.svg" alt="logo">
            <p>Логотип</p>
        </div>
        <div class="info__catalog">
            <p>Каталог</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.info {
    display: flex;
    align-items: center;
    gap: 8px;

    &__logo {
        padding: 0 24px;
        display: flex;
        gap: 11px;
        align-items: center;

        img {
            padding: 3px;
        }

        p {
            font-size: 16px;
            font-weight: 400;
        }
    }

    &__catalog {
        height: 48px;
        padding: 8px 24px;
        border: 1px solid #73AFF4;
        border-radius: 8px;
        font-size: $md-font-size;
        font-weight: 500;
        display: flex;
        align-items: center;
    }
}

@media(max-width: 800px) {
    .info {
        display: none;
    }
}
</style>