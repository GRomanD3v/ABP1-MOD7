<script setup>
import { defineProps } from 'vue';

defineProps({
    personajeData: {
        type: Object,
        required: true
    }
});
</script>

<template>
    <div class="card h-100 shadow-sm border-0">
        <div class="ratio ratio-1x1"> 
            <img 
              :src="personajeData.imagen" 
              class="w-100 h-100 object-fit-cover" 
              :alt="`Imagen de ${personajeData.nombre}`"
            >
        </div>
        <div class="card-body">
            <h5 class="card-title text-grey mb-2">
                {{ personajeData.nombre }}
                <span class="badge bg-secondary ms-2">ID: {{ personajeData.id }}</span>
            </h5>

            <p class="card-text text-muted">
                {{ personajeData.descripcion }}
            </p>
        </div>

        <div class="card-footer bg-white border-top-0">
            <small class="text-danger">Cazador de Demonios</small>
        </div>

    </div>
</template>

<style scoped>

.object-fit-cover {
    object-fit: cover;
}    
.card-title {
    font-weight: 700;
}
</style>