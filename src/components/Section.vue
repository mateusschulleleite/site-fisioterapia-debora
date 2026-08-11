<template>
    <section>
        <motion.div
            :class="contentClass"
            :initial="{ opacity: 0, y: 60 }"
            :while-in-view="{ opacity: 1, y: 0 }"
            :viewport="{ once: true }"
            :transition="{ duration: 0.6 }"
        >
            <slot></slot>
        </motion.div>
    </section>
</template>

<script setup>
import { motion } from "motion-v";

defineProps({
    contentClass: String,
});
</script>

<style lang="scss" scoped>
section {
    padding: 25px 20px;
    background: #fbf7f3;

    @media (min-width: 1024px) {
        padding: 25px 50px;
    }

    @media (min-width: 1200px) {
        padding: 25px 70px;
    }

    @media (min-width: 1400px) {
        padding: 25px 100px;
    }

    @media (min-width: 1600px) {
        padding: 25px 150px;
    }

    @media (min-width: 1920px) {
        padding: 25px 250px;
    }
}
</style>
