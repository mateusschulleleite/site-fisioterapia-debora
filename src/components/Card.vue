<template>
    <div class="card">
        <div class="card__icon">
            <slot name="icon"></slot>
        </div>
        <div class="card__content">
            <h4>{{ title }}</h4>
            <p>{{ description }}</p>
        </div>
    </div>
</template>

<script setup lang="js">
    const props = defineProps({
        title: String,
        description: Number
    })
</script>

<style lang="scss" scoped>
    .card {
        background: #fff;
        border-radius: 10px;
        padding: 20px;
        border: solid 1px #e9dedb;
        font-family: "Montserrat", sans-serif !important;
        display: flex;
        gap: 10px;

        h4 {
            font-size: 1rem;
            color: #681f24;
        }

        p {
            margin-top: 5px;
            font-size: 0.85rem;
            color: #4a1619;
        }
    }
</style>