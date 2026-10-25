<script setup>
const emit = defineEmits(['navigate'])

function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}
</script>

<template>
  <footer>
    <button class="back-top" @click="scrollToTop">
      Voltar ao início
    </button>
    <div class="footer-links">
      <div>
        <h3>Conheça-nos</h3>
        <a>Sobre a Amazon</a>
        <a>Carreiras</a>
        <a>Amazon Science</a>
      </div>
      <div>
        <h3>Ganhe dinheiro conosco</h3>
        <a>Venda na Amazon</a>
        <a>Proteja e construa a sua marca</a>
        <a>Publique seus livros</a>
      </div>
      <div>
        <h3>Pagamento</h3>
        <a>Meios de Pagamento</a>
        <a>Compre com Pontos</a>
        <a>Cartão de Crédito</a>
      </div>
      <div>
        <h3>Deixe-nos ajudar você</h3>
        <a>Sua conta</a>
        <a>Frete e prazo de entrega</a>
        <a>Ajuda</a>
      </div>
    </div>
    <button class="footer-logo" @click="emit('navigate', 'home')">amazon</button>
    <div class="legal">
      Condições de Uso &nbsp; | &nbsp; Notificação de Privacidade &nbsp; | &nbsp; Cookies<br />
      © 2021-2026 Amazon.com, Inc. ou suas afiliadas
    </div>
  </footer>
</template>
