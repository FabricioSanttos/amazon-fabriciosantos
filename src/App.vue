<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import AmazonHeader from '@/components/AmazonHeader.vue'
import AmazonFooter from '@/components/AmazonFooter.vue'
import MenuOverlay from '@/components/MenuOverlay.vue'
import HomeView from '@/views/HomeView.vue'
import ProductView from '@/views/ProductView.vue'
import LoginView from '@/views/LoginView.vue'

const screen = ref('home')
const menuOpen = ref(false)

function navigate(next) {
  window.location.hash = next === 'home' ? '/' : next === 'product' ? '/produto' : '/login'
  screen.value = next
  menuOpen.value = false
  window.scrollTo(0, 0)
}

function syncHash() {
  const hash = window.location.hash.replace('#/', '')
  if (hash === 'produto') {
    screen.value = 'product'
  } else if (hash === 'login') {
    screen.value = 'login'
  } else {
    screen.value = 'home'
  }
  window.scrollTo(0, 0)
}

onMounted(() => {
  syncHash()
  window.addEventListener('hashchange', syncHash)
})

onUnmounted(() => {
  window.removeEventListener('hashchange', syncHash)
})
</script>

<template>
  <!-- Tela de Login -->
  <LoginView
    v-if="screen === 'login'"
    @navigate="navigate"
  />

  <!-- Layout Principal (Home e Produto) -->
  <template v-else>
    <AmazonHeader
      @navigate="navigate"
      @open-menu="menuOpen = true"
    />

    <HomeView
      v-if="screen === 'home'"
      @navigate="navigate"
    />

    <ProductView
      v-else-if="screen === 'product'"
    />

    <AmazonFooter
      @navigate="navigate"
    />

    <MenuOverlay
      :is-open="menuOpen"
      @close="menuOpen = false"
    />
  </template>
</template>
