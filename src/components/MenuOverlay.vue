<script setup>
defineProps({
  isOpen: {
    type: Boolean,
    default: false
  }
})

const emit = defineEmits(['close'])

const asset = (name) => `${import.meta.env.BASE_URL}assets/amazon/${name}.png`
</script>

<template>
  <div
    v-if="isOpen"
    class="menu-overlay"
    role="dialog"
    aria-modal="true"
    aria-label="Menu Todos"
    @click="emit('close')"
  >
    <img :src="asset('menu-open')" alt="Menu da Amazon aberto" />
    <button class="menu-close" aria-label="Fechar menu" @click="emit('close')">×</button>
  </div>
</template>
