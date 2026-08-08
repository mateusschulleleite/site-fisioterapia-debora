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