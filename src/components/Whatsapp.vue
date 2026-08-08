<template>
    <div class="whatsapp">
        <a
            aria-label="Entrar em contato pelo WhatsApp"
            target="blank"
            href="https://wa.me/5548998276518?text=Ol%C3%A1%2C%20gostaria%20de%20saber%20mais%20sobre%20a%20consulta%20de%20fisioterapia."
        >
            <img src="../assets/iconWhatsapp.png" />
        </a>
    </div>
</template>
<style lang="scss">
.whatsapp {
    position: fixed;
    bottom: 5px;
    right: 5px;
    width: 60px;
    z-index: 10;
    animation: blink 2s infinite;
}

@keyframes blink {
    50% {
        opacity: 1;
        transform: scale(1.1);
    }
}
</style>
