<script setup>
const asset = (name) => `${import.meta.env.BASE_URL}assets/amazon/${name}.png`
</script>

<template>
  <main class="product-page">
    <img
      class="product-section"
      :src="asset('product-main')"
      alt="Bundle Nintendo Switch 2 e Mario Kart World"
    />
    <section class="product-banner">
      <img :src="asset('switch-banner')" alt="Nintendo Switch 2 em destaque" />
    </section>
    <img
      class="product-section"
      :src="asset('product-related')"
      alt="Produtos relacionados comprados pelos clientes"
    />
    <img
      class="product-section"
      :src="asset('product-reviews')"
      alt="Avaliações dos clientes"
    />
  </main>
</template>
