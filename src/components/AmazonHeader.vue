<script setup>
import { ref } from 'vue'

const emit = defineEmits(['navigate', 'open-menu'])

const search = ref('')

function submitSearch() {
  emit('navigate', 'product')
}
</script>

<template>
  <header>
    <div class="topbar">
      <button class="logo" @click="emit('navigate', 'home')" aria-label="Amazon início">
        amazon<span>.com.br</span>
      </button>
      <button class="delivery" aria-label="Alterar endereço de entrega">
        <span class="pin">⌖</span>
        <span>Enviar para José<br /><strong>Juazeiro do Norte 63038-345</strong></span>
      </button>
      <form class="search" @submit.prevent="submitSearch">
        <select aria-label="Categoria da pesquisa" default-value="Todos">
          <option>Todos</option>
          <option>Games</option>
          <option>Eletrônicos</option>
        </select>
        <input
          v-model="search"
          placeholder="Pesquisar Amazon.com.br"
          aria-label="Pesquisar Amazon.com.br"
        />
        <button type="submit" aria-label="Pesquisar">⌕</button>
      </form>
      <button class="account" @click="emit('navigate', 'login')">
        Olá, faça seu login<br /><strong>Contas e Listas⌄</strong>
      </button>
      <button class="orders">
        Devoluções<br /><strong>e Pedidos</strong>
      </button>
      <button class="cart" aria-label="Carrinho">
        <b>0</b>
        <i class="cart-icon" aria-hidden="true" />
        <span>Carrinho</span>
      </button>
    </div>

    <nav class="subnav" aria-label="Navegação principal">
      <button class="all" @click="emit('open-menu')">
        <span>☰</span> Todos
      </button>
      <button>Ofertas do Dia</button>
      <button>Mais Vendidos</button>
      <button>Games</button>
      <button>Livros</button>
      <button>Música</button>
      <button>Casa</button>
      <button>Eletrônicos</button>
      <button>Brinquedos e Jogos</button>
      <strong>Jovem Sherlock - Assista agora</strong>
    </nav>
  </header>
</template>
