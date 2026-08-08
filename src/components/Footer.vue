<template>
    <Section>
        <Logo />
        <div>
            <ul>
                <li @click="scrollToSection('home')">Home</li>
                <li @click="scrollToSection('treatments')">Tratamentos</li>
                <li @click="scrollToSection('methods')">Método</li>
                <li @click="scrollToSection('reviews')">Avaliações</li>
                <li>
                    <a
                        target="_blank"
                        href="https://wa.me/5548998276518?text=Ol%C3%A1%2C%20gostaria%20de%20saber%20mais%20sobre%20a%20consulta%20de%20fisioterapia."
                    >
                        Agendar Avaliação
                    </a>
                </li>
            </ul>
        </div>
        <div class="developer">Desenvolvido por <b>Mateus Schulle Leite</b></div>
    </Section>
</template>

<script setup lang="js">
import Logo from "./Logo.vue";
import Section from "./Section.vue";

function scrollToSection(section) {
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
section {
    font-family: "Montserrat", sans-serif !important;

    .logo {
        max-width: 150px;
        margin: 0 auto;
    }

    ul {
        color: #681f24;
        font-weight: 600;
        font-size: 0.85rem;
        display: flex;
        flex-direction: column;

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

    .developer {
        margin-top: 20px;
        font-size: 0.9rem;
        text-align: center;
        font-weight: 300;
        color: #681f24;
        border-top: #681f24 solid 1px;
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
