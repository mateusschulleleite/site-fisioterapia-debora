<template>
    <Section class="treatments">
        <SectionTitle>Tratamentos</SectionTitle>
        <ul>
            <Card title="Dores na coluna" description="Alívio, mobilidade e orientação para sua rotina.">
                <template #icon>
                    <CheckCircleIcon></CheckCircleIcon>
                </template>
            </Card>
            <Card title="Reabilitação" description="Retorno gradual após lesões, cirurgias ou pausas.">
                <template #icon>
                    <CheckCircleIcon></CheckCircleIcon>
                </template>
            </Card>
            <Card title="Prevenção" description="Fortalecimento para mover melhor e evitar recidivas.">
                <template #icon>
                    <CheckCircleIcon></CheckCircleIcon>
                </template>
            </Card>
        </ul>
    </Section>
</template>

<script setup lang="js">
import { CheckCircleIcon } from '@heroicons/vue/16/solid';
import Card from './Card.vue';
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<style scoped lang="scss">
section {
    ul {
        display: flex;
        flex-direction: column;
        gap: 15px;

        .card {
            .card__icon {
                svg {
                    width: 25px;
                    height: 25px;
                    color: #681F24;
                }
            }
        }
    }

    @media (min-width: 1024px) {
        ul {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            flex-direction: row;

            .card {
                flex-direction: column;
            }
        }
    }
}
</style>