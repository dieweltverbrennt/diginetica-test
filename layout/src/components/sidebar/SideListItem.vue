<template>
    <div class="checkbox">
        <label class="checkbox__content">
            <input type="checkbox" :id="index" :name="item.name" v-model="item.check" />
            <p>{{ item.name }}</p>
        </label>
        <span>{{ item.count }}</span>
    </div>
</template>

<script>
export default {
    props: {
        item: {
            type: Object,
            default: null
        },
        index: {
            type: Number,
            default: 1
        }
    }
}
</script>

<style lang="scss" scoped>
.checkbox {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-right: $mid-gap;

    &__content {
        display: flex;
        gap: 12px;

        input {
            appearance: none;
            width: 20px;
            height: 20px;
            border: 1px solid $border-color;
            border-radius: 3px;

            &:checked {
                background-color: $color-primary;
                border-color: $color-primary;
                position: relative;

                &:after {
                    content: "";
                    position: absolute;
                    top: 50%;
                    transform: translate(-50%, -50%);
                    left: 50%;
                    background-image: url('@/assets/images/check.svg');
                    background-repeat: no-repeat;
                    background-size: 10px;
                    width: 10px;
                    height: 10px;
                }
            }

            &:hover {
                border-color: $color-primary;
            }
        }
    }
}
</style>