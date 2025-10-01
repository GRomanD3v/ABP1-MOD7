# Ejercicio ABP1
### Ruta de repositorio: 
### Autor: Gonzalo Román Reyes

---
### Documentación: Lista de Personajes de Demon Slayer
Este proyecto fue construido con Vue 3 (Composition API y `<script setup>`) y Vite, e implementa una lista interactiva de personajes de Demon Slayer, cumpliendo con todos los requisitos de arquitectura y manejo de datos. La interfaz utiliza Bootstrap 5 para el diseño.

---

### Requisitos del Ejercicio Cumplidos

### 1. Utilización de Vue y sus Directivas
Se emplearon directivas clave de Vue para la renderización y el flujo de datos:

- v-for: Utilizado en ListaPersonajes.vue para iterar sobre el arreglo de personajes y generar dinámicamente el markup de cada tarjeta.

- v-bind (:): Esencial para pasar datos complejos entre componentes (como props) y para asignar valores dinámicos a atributos HTML, como la ruta de la imagen (:src) y la clave de la lista (:key).

- Interpolación ({{ }}): Usada en PersonajeItem.vue para mostrar de forma dinámica el nombre, ID y descripción de cada personaje.

---

### 2. Estructura Vue y Componentes

Se creó una estructura de tres componentes anidados para separar la lógica de datos de la presentación, lo que supera el requisito mínimo de dos componentes:

- App.vue (Componente Raíz): Contiene la lógica principal, inicializa el estado con los datos y orquesta el flujo de la aplicación.

- ListaPersonajes.vue (Componente Iterador): Recibe la lista completa y usa v-for para renderizar el contenedor de la grilla de Bootstrap, pasando cada objeto individual al componente de presentación.

- PersonajeItem.vue (Componente de Presentación): Recibe los datos de un único personaje y se encarga de darle formato visual con las clases de card de Bootstrap.

---

### 3. Arreglo para Recorrer Nombre y Descripción

El arreglo de datos, llamado personajesDS, está definido de forma reactiva en el componente raíz (App.vue) usando ref(). Cada objeto dentro de este arreglo contiene las propiedades nombre y descripcion, las cuales son recorridas y mostradas.

La propiedad descripcion y nombre se muestran dinámicamente en el template de PersonajeItem.vue a través de la interpolación:

```
<h5 class="card-title">{{ personajeData.nombre }}</h5>
<p class="card-text">{{ personajeData.descripcion }}</p>
```
---

### 4. Definición de Datos en un Objeto "Data" y Muestra Dinámica

Los datos están definidos en la sección`<script setup>` de App.vue utilizando la función ref(), que es la manera recomendada en Vue 3 para declarar estado reactivo (equivalente moderno del objeto data de Options API).

- Ubicación de Datos: Los datos existen en la referencia reactiva personajesDS en App.vue.

- Muestra Dinámica: Los datos se muestran dinámicamente en el template de PersonajeItem.vue (el componente de presentación) utilizando la propiedad personajeData recibida a través de props.

---

### 5. Paso de Datos por Props

El flujo de datos se maneja exclusivamente a través de props, asegurando un flujo de información unidireccional y predecible:

- Paso 1 (Array): Desde App.vue, el arreglo completo (personajesDS) es pasado como la prop lista-de-personajes a ListaPersonajes.vue.

- Paso 2 (Objeto): Dentro del loop v-for en ListaPersonajes.vue, cada objeto individual (personaje) es pasado como la prop personaje-data a PersonajeItem.vue para su renderización final.
