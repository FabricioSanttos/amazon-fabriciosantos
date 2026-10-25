<script setup>
const emit = defineEmits(['navigate'])

const asset = (name) => `${import.meta.env.BASE_URL}assets/amazon/${name}.png`
</script>

<template>
  <main class="home">
    <section class="hero-wrap">
      <img :src="asset('hero-echo')" alt="Echo Pop com Alexa e frete grátis Prime" />
    </section>
    <section class="home-content">
      <img :src="asset('home-easter-grid')" alt="Ofertas de Páscoa, Kindle, cartão Prime e dispositivos Alexa" />
      <img :src="asset('home-products')" alt="Produtos de cozinha e categorias mais amadas" />
      <button class="switch-feature" @click="emit('navigate', 'product')" aria-label="Ver Nintendo Switch 2">
        <img :src="asset('switch-banner')" alt="Nintendo Switch 2" />
      </button>
      <img :src="asset('home-categories')" alt="Novidades na Amazon por categoria" />
    </section>
  </main>
</template>
