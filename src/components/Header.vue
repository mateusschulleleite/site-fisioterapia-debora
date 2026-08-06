<template>
    <header>
        <Logo />
        <h1>
            Dra. Débora <br> Fratoni
        </h1>
        <div v-if="menuToggle" ref="menu" class="header__menu">
            <ul>
                <li>Home</li>
                <li>Sobre</li>
                <li>Tratamentos</li>
                <li>Método</li>
                <li>Agendar Avaliação</li>
            </ul>
        </div>
        <div class="header__icon" @click="toggleMenu">
            <Bars3Icon v-if="!menuToggle"/>
            <XMarkIcon v-if="menuToggle"/>
        </div>
    </header>
</template>

<script setup lang="js">
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/16/solid';
import Logo from './Logo.vue';
import { ref } from 'vue';

const menuToggle = ref(false)

function toggleMenu() {
  menuToggle.value = !menuToggle.value
}

</script>

<style lang="scss">
header  {
    border-bottom: 1px solid #8E2027;
    padding: 10px 20px;
    display: flex;
    align-items: center;
    position: relative;
    background-color: #FBF7F2;

    .logo {
        max-width: 65px;
    }

    h1 {
        margin-left: 10px;
        font-size: 1.1rem;
        color: #681F24;
        line-height: 18px;
    }

    .header__menu {
        position: absolute;
        width: 100%;
        left: 0;
        top: 100%;
        padding: 5px;
        z-index: 2;

        ul {
            background-color: #FBF7F2;
            font-family: "Montserrat", sans-serif !important;
            color: #681F24;
            font-weight: 600;
            font-size: 0.85rem;
            padding: 15px 15px;
            box-shadow: 0px 0px 10px 1px #681f2437;
            display: flex;
            flex-direction: column;
            gap: 13px;
            border-radius: 8px;

            :last-child {
                background-color: #681F24;
                color: #FBF7F2;
                padding: 10px;
                border-radius: 4px;
                display: inline-block;
                width: fit-content;
                box-shadow: 0px 0px 10px 1px #681f2437;
            }
        }
    }

    .header__icon {
        color: #681F24;
        flex-grow: 1;
        justify-content: end;
        display: flex;

        svg {
            width: 30px;
            height: 30px;
        }

    }
}
</style>