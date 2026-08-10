<template>
    <Section class="methods">
        <SectionTitle>Métodos de Cuidado</SectionTitle>
        <div>
            <div class="methods__description">
                <span>MÉTODOS DE CUIDADO</span>
                <h3>Uma experiência clara desde a primeira consulta.</h3>
            </div>
            <ul>
                <Card
                    title="Avaliação completa"
                    description="Entendimento da dor, rotina e objetivos."
                >
                    <template #icon>
                        <span>01</span>
                    </template>
                </Card>
                <Card title="Plano" description="Conduta individualizada e explicada com clareza.">
                    <template #icon>
                        <span>02</span>
                    </template>
                </Card>
                <Card
                    title="Acompanhamento"
                    description="Ajustes frequentes para ganhar função com segurança."
                >
                    <template #icon>
                        <span>03</span>
                    </template>
                </Card>
            </ul>
        </div>
    </Section>
</template>

<script setup lang="js">
import Card from "./Card.vue";
import Section from "./Section.vue";
import SectionTitle from "./SectionTitle.vue";
</script>

<style scoped lang="scss">
section {
    background: #ffffff;

    > div {
        .methods__description {
            display: none;
        }

        ul {
            display: flex;
            flex-direction: column;
            gap: 15px;

            .card {
                background: #fbf7f2;

                .card__icon {
                    span {
                        background-color: #681f24;
                        color: #fbf7f2;
                        width: 30px;
                        height: 30px;
                        border-radius: 50%;
                        display: flex;
                        align-items: center;
                        justify-content: center;
                    }
                }
            }
        }
    }

    @media (min-width: 1024px) {
        h2 {
            display: none;
        }

        > div {
            display: grid;
            grid-template-columns: 1fr 1fr;

            > div {
                display: flex;
                flex-direction: column;

                > span {
                    font-family: "Montserrat", sans-serif !important;
                    color: #8e2027;
                    font-weight: 700;
                    font-size: 0.8rem;
                    margin-bottom: 10px;

                    &::before {
                        content: "";
                        display: inline-block;
                        width: 34px;
                        height: 2px;
                        background-color: #8e2027;
                        margin-right: 8px;
                        vertical-align: middle;
                    }
                }
            }

            h3 {
                color: #681f24;
                font-weight: 400;
            }

            ul {
                display: flex;
                flex-direction: column;
                gap: 15px;

                .card {
                    background: #fbf7f2;

                    .card__icon {
                        span {
                            background-color: #681f24;
                            color: #fbf7f2;
                            width: 30px;
                            height: 30px;
                            border-radius: 50%;
                            display: flex;
                            align-items: center;
                            justify-content: center;
                        }
                    }
                }
            }
        }
    }
}
</style>
