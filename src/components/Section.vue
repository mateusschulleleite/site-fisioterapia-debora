<template>
    <section>
        <slot></slot>
    </section>
</template>

<style lang="scss" scoped>
    section {
        padding: 25px 20px;
        background: #FBF7F3;

        @media (min-width: 1024px) {
            padding: 25px 50px;
            
        }
    }
</style>