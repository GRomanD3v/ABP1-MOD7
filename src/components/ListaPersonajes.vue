<script setup>
import PersonajeItem from "./PersonajeItem.vue";
import { defineProps } from "vue";

defineProps({
  listaDePersonajes: {
    type: Array,
    required: true,
  },
});
</script>

<template>
  <div class="row g-4">
    <div 
      class="col-12 col-md-6" 
      v-for="personaje in listaDePersonajes" 
      :key="personaje.id"
    >
      <PersonajeItem :personaje-data="personaje" />
    </div>
  </div>
</template>

<style scoped></style>