<template>
    <Section class="reviews">
        <SectionTitle>Avaliações de Pacientes</SectionTitle>

        <Carousel :items-to-show="1" :wrap-around="true" :autoplay="5000" :breakpoints="{
            1024: {
                itemsToShow: 3,
                gap: 24
            },
            1200: {
                itemsToShow: 4,
                gap: 30
            },
            1400: {
                itemsToShow: 5,
                gap: 30
            }
        }">
            <Slide>
                <Card title="Mariana Souza"
                    description="Cheguei com muita dor na lombar e dificuldade para trabalhar sentada. O atendimento foi cuidadoso, o plano fez sentido para minha rotina e senti melhora já nas primeiras semanas." />
            </Slide>

            <Slide>
                <Card title="Rafael Almeida"
                    description="Procurei a fisioterapia depois de uma lesão no joelho. Fui acompanhado com atenção em cada etapa e consegui voltar a treinar com mais segurança e confiança." />
            </Slide>

            <Slide>
                <Card title="Camila Ferreira"
                    description="Gostei muito da forma como tudo foi explicado. Entendi a origem da dor, aprendi exercícios simples para fazer em casa e hoje me movimento com muito mais tranquilidade." />
            </Slide>

            <Slide>
                <Card title="Bruno Martins"
                    description="O tratamento foi muito bem conduzido. As sessões eram objetivas, os exercícios evoluíam no meu ritmo e percebi melhora real na mobilidade do ombro." />
            </Slide>

            <Slide>
                <Card title="Fernanda Lima"
                    description="Depois de meses com dor no pescoço, finalmente encontrei um acompanhamento que olhou para minha postura, rotina e hábitos. A diferença no dia a dia foi enorme." />
            </Slide>

            <Slide>
                <Card title="Lucas Pereira"
                    description="Tive uma entorse no tornozelo e estava inseguro para voltar a correr. Com o acompanhamento, ganhei força, estabilidade e voltei aos treinos sem medo." />
            </Slide>

            <Slide>
                <Card title="Juliana Rocha"
                    description="O atendimento foi acolhedor desde a primeira avaliação. Senti que minhas queixas foram realmente ouvidas e o tratamento evoluiu de forma leve e eficiente." />
            </Slide>

            <Slide>
                <Card title="André Oliveira"
                    description="As dores no ombro atrapalhavam até tarefas simples. Com as sessões e os exercícios orientados, recuperei movimento e consegui voltar à rotina normal." />
            </Slide>

            <Slide>
                <Card title="Patrícia Gomes"
                    description="Fiz fisioterapia no pós-operatório e me senti segura durante todo o processo. Cada exercício era explicado com calma e respeitava minha recuperação." />
            </Slide>

            <Slide>
                <Card title="Thiago Mendes"
                    description="Eu tinha dor constante por causa da rotina no computador. O tratamento ajudou muito, principalmente pelas orientações práticas para corrigir hábitos no dia a dia." />
            </Slide>

            <template #addons>
                <Navigation />
            </template>
        </Carousel>
    </Section>
</template>

<script setup lang="js">
import 'vue3-carousel/carousel.css'
import { Carousel, Slide, Navigation } from 'vue3-carousel'

import Card from './Card.vue'
import Section from './Section.vue'
import SectionTitle from './SectionTitle.vue'
</script>

<style scoped lang="scss">
section {
    background: #6D272B;

    h2 {
        color: #FFFFFF;
    }

    .card {
        :deep(.card__content h4) {
            font-size: 1.2rem;
        }
    }
}
</style>