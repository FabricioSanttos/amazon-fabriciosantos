<script setup>
const emit = defineEmits(['navigate'])
</script>

<template>
  <main class="login-page">
    <button class="login-logo" @click="emit('navigate', 'home')" aria-label="Ir para a página inicial">
      amazon<span>.com.br</span>
    </button>
    <section class="login-card">
      <h1>Fazer login</h1>
      <label for="email">E-mail ou número de telefone</label>
      <input id="email" type="email" autofocus />
      <button class="continue">Continuar</button>
      <p>
        Ao continuar, você concorda com as <a>Condições de Uso</a> e a
        <a>Notificação de Privacidade</a> da Amazon.
      </p>
      <details>
        <summary>Precisa de ajuda?</summary>
        <a>Esqueci a senha</a>
      </details>
      <div class="business">
        <strong>Comprando para o trabalho?</strong>
        <a>Compre na Amazon Business</a>
      </div>
    </section>
    <div class="new">
      <span>Novo na Amazon?</span>
      <button>Criar sua conta da Amazon</button>
    </div>
    <div class="login-legal">
      <a>Condições de Uso</a>
      <a>Política de Privacidade</a>
      <a>Ajuda</a>
      <p>© 2021-2026 Amazon.com, Inc. ou suas afiliadas</p>
    </div>
  </main>
</template>
