<template>
    <div
        class="card"
        :class="{
            'card--expanded': isExpanded,
            'card--has-toggle': hasOverflow,
        }"
    >
        <div class="card__icon">
            <slot name="icon"></slot>
        </div>
        <div ref="contentRef" class="card__content">
            <h4>{{ title }}</h4>
            <p>{{ description }}</p>
        </div>
        <button
            v-if="hasOverflow"
            class="card__toggle"
            type="button"
            @click="isExpanded = !isExpanded"
        >
            {{ isExpanded ? 'Ver menos' : 'Ver mais...' }}
        </button>
    </div>
</template>

<script setup lang="js">
import { nextTick, onBeforeUnmount, onMounted, ref, watch } from 'vue';

const props = defineProps({
    title: String,
    description: String,
});

const CONTENT_MAX_HEIGHT = 200;
const contentRef = ref(null);
const hasOverflow = ref(false);
const isExpanded = ref(false);

const checkOverflow = () => {
    if (!contentRef.value) return;

    hasOverflow.value = contentRef.value.scrollHeight > CONTENT_MAX_HEIGHT;
};

onMounted(async () => {
    await nextTick();
    checkOverflow();
    window.addEventListener('resize', checkOverflow);
});

onBeforeUnmount(() => {
    window.removeEventListener('resize', checkOverflow);
});

watch(
    () => props.description,
    async () => {
        await nextTick();
        checkOverflow();
    },
);
</script>

<style lang="scss" scoped>
.card {
    background: #fff;
    border-radius: 10px;
    padding: 20px;
    border: solid 1px #e9dedb;
    font-family: "Montserrat", sans-serif !important;
    gap: 10px;
    transition: 300ms all;
    position: relative;

    &:hover {
        border: solid 1px #681f24;
        transform: scale(1.01);
    }

    &.card--has-toggle {
        padding-bottom: 34px;
    }

    .card__content {
        margin-top: 10px;
        max-height: 200px;
        overflow: hidden;

        h4 {
            font-size: 1rem;
            color: #681f24;
        }

        p {
            margin-top: 8px;
            font-size: 0.85rem;
            color: #4a1619;
            line-height: 20px;
            white-space: pre-line;
        }
    }

    &.card--expanded {
        .card__content {
            max-height: none;
        }
    }

    .card__toggle {
        position: absolute;
        bottom: 4px;
        right: 10px;
        border: 0;
        background: transparent;
        font-size: 0.75rem;
        font-weight: 600;
        color: #4a1619;
        cursor: pointer;
        font-family: "Montserrat", sans-serif !important;
        padding: 4px 0;
    }
}
</style>
