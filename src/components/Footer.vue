<template>
    <Section>
        <Logo />
        <div>
            <ul>
                <li>Home</li>
                <li>Sobre</li>
                <li>Tratamentos</li>
                <li>Método</li>
                <li>Agendar Avaliação</li>
            </ul>
        </div>
        <div class="developer">
            Desenvolvido por <b>Mateus Schulle Leite</b>
        </div>
    </Section>
</template>

<script setup lang="js">
import Logo from './Logo.vue';
import Section from './Section.vue';
</script>

<style scoped lang="scss">
section {
    font-family: "Montserrat", sans-serif !important;

    .logo {
        max-width: 150px;
        margin: 0 auto;
    }

    ul {
        color: #681F24;
        font-weight: 600;
        font-size: 0.85rem;
        display: flex;
        flex-direction: column;
        gap: 13px;

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

    .developer {
        margin-top: 20px;
        font-size: 0.9rem;
        text-align: center;
        font-weight: 300;
        color: #681F24;
        border-top: #681F24 solid 1px;
        padding-top: 10px;

        b {
            font-weight: 700;
        }
    }

    @media (min-width: 1024px) {
        ul {
            flex-direction: row;
            align-items: center;
            justify-content: center;
        }
    }
}
</style>