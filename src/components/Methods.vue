<template>
    <Section>
        <SectionTitle>Métodos de Cuidado</SectionTitle>
        <ul>
            <Card title="Avaliação completa" description="Entendimento da dor, rotina e objetivos.">
                <template #icon>
                    <span>01</span>
                </template>
            </Card>
            <Card title="Plano" description="Conduta individualizada e explicada com clareza.">
                <template #icon>
                    <span>02</span>
                </template>
            </Card>
            <Card title="Acompanhamento" description="Ajustes frequentes para ganhar função com segurança.">
                <template #icon>
                    <span>03</span>
                </template>
            </Card>
        </ul>
    </Section>
</template>

<script setup lang="js">
import Card from './Card.vue';
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<style scoped lang="scss">
    section {
        background: #ffffff;

        ul {
            display: flex;
            flex-direction: column;
            gap: 15px;

            .card {
                background: #FBF7F2;

                .card__icon {
                    span {
                        background-color: #681F24;
                        color: #FBF7F2;
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
</style>