<template>
    <div class="logo" :class="{ 'logo--scrolled': scrolled }">
        <img src="../assets/logo.png" />
    </div>
</template>

<script setup>
defineProps({
    scrolled: {
        type: Boolean,
        default: false
    }
})
</script>

<style scoped lang="scss">
.logo {
    transition: max-width 0.3s ease;

    &--scrolled {
        max-width: 65px !important;
    }
}
</style>