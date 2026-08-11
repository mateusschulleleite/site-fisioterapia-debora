<template>
    <header class="header" :class="{ 'header--scrolled': headerScrolled }">
        <Logo :scrolled="headerScrolled" />

        <div class="header__title">
            <h1>Dra. Débora Fratoni</h1>
            <span>FISIOTERAPIA INTEGRADA</span>
        </div>

        <nav class="header__menu" :class="{ 'header__menu--open': menuToggle }">
            <ul>
                <li title="Home" @click="scrollToSection('home')">Home</li>
                <li title="Tratamentos" @click="scrollToSection('treatments')">Tratamentos</li>
                <li title="Método" @click="scrollToSection('methods')">Método</li>
                <li title="Avaliações" @click="scrollToSection('reviews')">Avaliações</li>
                <li>
                    <a
                        aria-label="Entrar em contato pelo WhatsApp"
                        target="_blank"
                        href="https://wa.me/5548998276518?text=Ol%C3%A1%2C%20gostaria%20de%20saber%20mais%20sobre%20a%20consulta%20de%20fisioterapia."
                    >
                        Agendar Avaliação
                    </a>
                </li>
            </ul>
        </nav>

        <button class="header__icon" type="button" aria-label="Abrir menu" @click="toggleMenu">
            <Bars3Icon v-if="!menuToggle" />
            <XMarkIcon v-else />
        </button>
    </header>
</template>

<script setup>
import { ref } from "vue";
import Logo from "./Logo.vue";

const menuToggle = ref(false);

function toggleMenu() {
    menuToggle.value = !menuToggle.value;
}

const headerScrolled = ref(false);

function handleScroll() {
    headerScrolled.value = window.scrollY > 50;
}

window.addEventListener("scroll", handleScroll);

function scrollToSection(section) {
    menuToggle.value = false;

    const element = document.querySelector(`.${section}`);

    if (element) {
        window.scrollTo({
            top: element.offsetTop - 80,
            behavior: "smooth",
        });
    }
}
</script>

<style scoped lang="scss">
.header {
    position: fixed;
    top: 0;
    z-index: 3;
    width: 100%;
    display: flex;
    align-items: center;
    padding: 10px 20px;
    background-color: transparent;
    transition: 300ms all;

    &--scrolled {
        background-color: #fbf7f2 !important;
    }

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
            padding: 15px;
            border-radius: 8px;
            background-color: #fbf7f2;
            box-shadow: 0 0 10px 1px #681f2437;
            color: #681f24;
            font-family: "Montserrat", sans-serif;
            font-size: 0.85rem;
            font-weight: 600;

            li {
                cursor: pointer;
                transition: 400ms all;
                padding: 10px;
                border-radius: 4px;

                &:hover {
                    background-color: #681f24;
                    box-shadow: none;
                    color: #fbf7f2;
                }
            }

            li:last-child {
                width: fit-content;
                background-color: #681f24;
                box-shadow: 0 0 10px 1px #681f2437;

                &:hover {
                    background-color: #fbf7f2;
                    box-shadow: none;

                    a {
                        color: #681f24;
                    }
                }
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
            }
        }

        .header__icon {
            display: none;
        }
    }

    @media (min-width: 1200px) {
        padding: 5px 70px;
    }

    @media (min-width: 1400px) {
        padding: 5px 100px;
    }

    @media (min-width: 1600px) {
        padding: 5px 150px;
    }

    @media (min-width: 1920px) {
        padding: 5px 250px;
    }
}
</style>
