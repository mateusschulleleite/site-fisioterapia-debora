<template>
    <Section class="treatments" content-class="treatments__grid">
        <SectionTitle class="treatments__title">Como posso ajudar você e sua família?</SectionTitle>
        <div class="treatments__description">
            <p>Sou Fisioterapeuta com mestrado e especialização, dedicada a cuidar da saúde e do bem-estar em diferentes
                fases e necessidades da vida. Meu foco é oferecer um atendimento humanizado, seguro e baseado nas
                melhores técnicas científicas.
                <br><br>
                Confira as principais áreas em que atuo:
            </p>
        </div>
        <ul>
            <Card title="Fisioterapia Infantil e Neurofuncional"
                description="Acompanhamento especializado para o desenvolvimento saudável das crianças.
            
                A infância é uma fase cheia de descobertas e transformações. O acompanhamento fisioterapêutico ajuda bebês e crianças a vencerem desafios no movimento, na força e na coordenação, além de reabilitar condições neurológicas.

                O que atendo:

                Atrasos no desenvolvimento: Bebês que demoram para sentar, engatinhar ou andar.

                Condições e alterações neurológicas: Acompanhamento para Paralisia Cerebral, síndromes genéticas, rigidez ou fraqueza muscular.

                Estimulação precoce: Apoio para bebês prematuros ou que precisam de um incentivo extra para desenvolver seus movimentos.">
                <template #icon>
                    <PuzzlePieceIcon></PuzzlePieceIcon>
                </template>
            </Card>
            <Card title="Fisioterapia Respiratória"
                description="Cuidado para respirar melhor e viver com mais qualidade.

A fisioterapia respiratória auxilia na limpeza das vias aéreas, na melhora da capacidade pulmonar e no alívio de desconfortos causados por secreções ou cansaço respiratório.

O que atendo:

Problemas respiratórios em bebês e crianças: Secreção acumulada, gripes, bronquiolite e crises respiratórias.

Cuidado respiratório adulto: Recuperação de infecções pulmonares, falta de ar e fortalecimento dos músculos que nos ajudam a respirar.">
                <template #icon>
                    <CloudIcon></CloudIcon>
                </template>
            </Card>
            <Card title="Reabilitação Muscular e Articular (Ortopédica)"
                description="Tratamento para dores, lesões e prevenção.

Tratamento focado em aliviar dores, recuperar movimentos e devolver a autonomia para as atividades do dia a dia.

O que atendo:

D dores nas costas, pescoço, ombros ou joelhos.

Recuperação de lesões musculares, entorses e pós-operatórios.

Dificuldade de movimento por desgaste ou alteração na postura.

Uso de Terapia Manual (técnicas de massagem e alívio de tensões musculares e da fáscia) para aliviar dores persistentes.">
                <template #icon>
                    <WrenchScrewdriverIcon></WrenchScrewdriverIcon>
                </template>
            </Card>
            <Card title="Pilates Clínico e Fortalecimento"
                description="Movimento consciente para prevenir dores e melhorar a postura.

O Pilates adaptado para a fisioterapia ajuda no fortalecimento muscular, no equilíbrio e no alívio de dores crônicas através de exercícios controlados e seguros.

Indicado para:

Fortalecer o corpo e melhorar a postura.

Prevenir dores nas costas e articulações.

Manter o corpo ativo com acompanhamento profissional individualizado.">
                <template #icon>
                    <HeartIcon></HeartIcon>
                </template>
            </Card>
            <Card title="Atendimento Domiciliar e Clínico"
                description="Para sua maior comodidade e conforto, os atendimentos podem ser realizados em consultório ou no aconchego do seu lar, ideal para crianças, idosos ou pessoas com dificuldade de locomoção.">
                <template #icon>
                    <HomeIcon></HomeIcon>
                </template>
            </Card>
        </ul>
    </Section>
</template>

<script setup lang="js">
import { ArrowsPointingOutIcon, BoltIcon, CheckCircleIcon, CloudIcon, HeartIcon, HomeIcon, PuzzlePieceIcon, ScaleIcon, WrenchScrewdriverIcon } from '@heroicons/vue/16/solid';
import Card from './Card.vue';
import Section from './Section.vue';
import SectionTitle from './SectionTitle.vue';
</script>

<style scoped lang="scss">
.treatments {
    .treatments__description {
        font-size: 0.85rem;
        color: #4a1619;
        font-family: "Montserrat", sans-serif !important;
        line-height: 20px;
        margin-bottom: 10px;
    }

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
        :deep(.treatments__grid) {
            display: grid;
            grid-template-columns: 1fr 2fr;
            grid-template-rows: auto 1fr;
        }

        .treatments__title {
            grid-column: 1 / 3;
            grid-row: 1;
        }

        .treatments__description {
            grid-column: 1;
            grid-row: 2;
        }

        ul {
            grid-column: 2;
            grid-row: 2;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            align-items: start;
            margin-left: 20px;

            .card {
                flex-direction: column;
            }
        }
    }
}
</style>
