<template>
    <header>
        <Logo :scrolled="headerScrolled" />

        <div class="header__title">
            <h1>Dra. Débora Fratoni</h1>
            <span>FISIOTERAPIA INTEGRADA</span>
        </div>

        <nav
            class="header__menu"
            :class="{ 'header__menu--open': menuToggle }"
        >
            <ul>
                <li>Home</li>
                <li>Sobre</li>
                <li>Tratamentos</li>
                <li>Método</li>
                <li>Agendar Avaliação</li>
            </ul>
        </nav>

        <button
            class="header__icon"
            type="button"
            aria-label="Abrir menu"
            @click="toggleMenu"
        >
            <Bars3Icon v-if="!menuToggle" />
            <XMarkIcon v-else />
        </button>
    </header>
</template>

<script setup>
import { ref } from 'vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/16/solid'
import Logo from './Logo.vue'

const menuToggle = ref(false)

function toggleMenu() {
    menuToggle.value = !menuToggle.value
}

const headerScrolled = ref(false)

function handleScroll() {
    headerScrolled.value = window.scrollY > 50
}

window.addEventListener('scroll', handleScroll)
</script>

<style scoped lang="scss">
header {
    position: fixed;
    top: 0;
    z-index: 3;
    width: 100%;
    display: flex;
    align-items: center;
    padding: 10px 20px;
    border-bottom: 1px solid #8e2027;
    background-color: #fbf7f2;

    .logo {
        max-width: 65px;
    }

    .header__title {
        max-width: 150px;
        margin-left: 10px;

        h1 {
            color: #681f24;
            font-size: 1.1rem;
            line-height: 18px;
        }

        span {
            display: none;
        }
    }

    .header__menu {
        display: none;
        position: absolute;
        top: 100%;
        left: 0;
        z-index: 2;
        width: 100%;
        padding: 5px;

        &--open {
            display: block;
        }

        ul {
            display: flex;
            flex-direction: column;
            gap: 13px;
            padding: 15px;
            border-radius: 8px;
            background-color: #fbf7f2;
            box-shadow: 0 0 10px 1px #681f2437;
            color: #681f24;
            font-family: "Montserrat", sans-serif;
            font-size: 0.85rem;
            font-weight: 600;

            li:last-child {
                width: fit-content;
                padding: 10px;
                border-radius: 4px;
                background-color: #681f24;
                box-shadow: 0 0 10px 1px #681f2437;
                color: #fbf7f2;
            }
        }
    }

    .header__icon {
        display: flex;
        flex-grow: 1;
        justify-content: flex-end;
        padding: 0;
        border: none;
        background: transparent;
        color: #681f24;
        cursor: pointer;

        svg {
            width: 30px;
            height: 30px;
        }
    }

    @media (min-width: 1024px) {
        padding: 10px 50px;

        .logo {
            max-width: 100px;
        }

        .header__title {
            max-width: 400px;
            margin-left: 20px;

            h1 {
                font-size: 1.3rem;
            }

            span {
                display: inline-block;
                margin-top: 7px;
                color: #4a1619;
                font-family: "Montserrat", sans-serif;
                font-size: 0.7rem;
                font-weight: 300;
            }
        }

        .header__menu {
            display: block;
            position: static;
            width: auto;
            margin-left: auto;
            padding: 0;

            ul {
                flex-direction: row;
                align-items: center;
                padding: 0;
                background: transparent;
                box-shadow: none;
                gap: 20px;
            }
        }

        .header__icon {
            display: none;
        }
    }
}
</style>