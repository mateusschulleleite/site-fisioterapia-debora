<template>
    <div class="home">
        <div class="home__content">
            <span>FISIOTERAPIA INTEGRADA</span>
            <h2>Movimento com segurança e cuidado.</h2>
            <p>Atendimento individual para dor, reabilitação e prevenção, com plano criado para você.</p>
            <button>Agendar pelo Whatsapp</button>
        </div>
    </div>
</template>

<style scoped lang="scss">
.home {
    margin-top: 76px;
    position: relative;
    overflow: hidden;
    background-color: #fbf7f2;
    padding: 45px 20px 35px;
    background-image: url("../assets/home.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 50% center;

    &::before {
        content: "";
        position: absolute;
        inset: 0;
        background: linear-gradient(90deg,
                #fbf7f2 0%,     
                rgba(251, 247, 242, 0.86) 40%,
                rgba(251, 247, 242, 0) 100%);
    }

    .home__content {
        position: relative;
        z-index: 1;
        max-width: 430px;

        span {
            font-family: "Montserrat", sans-serif !important;
            color: #8e2027;
            font-weight: 700;
            font-size: 0.8rem;

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

        h2 {
            margin-top: 10px;
            color: #681f24;
            font-weight: 500;
            font-size: 2.3rem;
            line-height: 1.12;
        }

        p {
            margin-top: 12px;
            font-size: 0.95rem;
            color: #4a1619;
            width: 300px;
            line-height: 1.65;
            font-family: "Montserrat", sans-serif !important;
        }

        button {
            background-color: #681f24;
            font-family: "Montserrat", sans-serif !important;
            font-weight: 600;
            margin-top: 18px;
            color: #fbf7f2;
            padding: 16px 10px;
            border-radius: 4px;
            border: none;
            box-shadow: 0px 0px 10px 1px #681f2437;
            width: 100%;
        }
    }

    @media (min-width: 1024px) {
        margin-top: 101px;
        padding: 45px 50px 150px;
        background-position: 100% 12%;
        background-size: cover;


        &::before {
            content: "";
            background: linear-gradient(90deg,
                    #fbf7f2 0%,
                    rgba(251, 247, 242, 0.86) 40%,
                    rgba(251, 247, 242, 0) 100%);
        }

        .home__content {
            max-width: 500px;

            h2 {
                font-size: 2.7rem;
            }

            p {
                font-size: 1.2rem;
            }

            button {
                width: fit-content;
            }
        }
    }

    @media (min-width: 1200px) {
        margin-top: 91px;
        padding: 60px 70px 150px;

        .home__content {
            h2 {
                font-size: 3rem;
            }

            p {
                font-size: 1rem;
                width: 360px;
            }
        }
    }

    @media (min-width: 1400px) {
        margin-top: 91px;
        padding: 60px 100px 150px;

        .home__content {
            max-width: 600px;

            h2 {
                font-size: 3.3rem;
            }

            p {
                font-size: 1.2rem;
                width: 500px;
            }

            button {
                width: fit-content;
            }

        }
    }

    @media (min-width: 1600px) {
        padding: 60px 150px 150px;
    }

    @media (min-width: 1920px) {
        padding: 60px 250px 150px;
    }
}
</style>