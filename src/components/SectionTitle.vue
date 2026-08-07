<template>
    <h2><slot></slot></h2>
</template>

<style scoped lang="scss">
    h2 {
        font-size: 1.5rem;
        color: #681f24;
        margin-bottom: 20px;
        font-weight: 500;
    }

    @media (min-width: 1024px) {
        h2 {
            font-size: 1.7rem;
        }
    }
</style>