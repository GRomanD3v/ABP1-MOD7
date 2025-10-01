<script setup>
import { ref } from 'vue';
import ListaPersonajes from './components/ListaPersonajes.vue';

// Personajes Demon Slayer 
const personajesDS = ref ([
    {
        id: '1',
        nombre: 'Tanjiro Kamado',
        descripcion: 'Protagonista. Cazador de demonios que usa la Respiración del Agua y del Sol para buscar la cura de su hermana.',
        imagen: '/images/tanjiro.avif'
    },
     {
        id: '2',
        nombre: 'Nezuko Kamado',
        descripcion: 'Hermana de Tanjiro, convertida en demonio, pero que mantiene su conciencia y protege a los humanos.',
        imagen: '/images/nezuko.webp'
  },
  {
        id: '3',
        nombre: 'Zenitsu Agatsuma',
        descripcion: 'Cazador cobarde pero que domina una poderosa técnica de la Respiración del Trueno cuando se desmaya.',
        imagen: '/images/zenitsu.webp'
  },
  {
        id: '4',
        nombre: 'Inosuke Hashibira',
        descripcion: 'Cazador criado por jabalíes. Impulsivo y usa la Respiración de la Bestia, luchando con dos espadas.',
        imagen: '/images/inosuke.webp'
  },
  {
        id: '5',
        nombre: 'Giyu Tomioka',
        descripcion: 'Pilar del Agua (Hashira). Serio y reservado, fue el primero en encontrar a Tanjiro y Nezuko.',
        imagen: '/images/giyu.webp'
  }
]);

</script>

<template>
  <div class="container py-5 bg-light">
    <h1 class="text-center mb-5 text-secondary border-bottom border-secondary pb-3">
      Personajes de Demon Slayer
    </h1>
    
    <ListaPersonajes :lista-de-personajes="personajesDS" />
  </div>
</template>

<style>
body {
  background-color: #f8f9fa; 
}
</style>