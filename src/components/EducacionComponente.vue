<script setup>
import { ref } from 'vue';
const fechaColor = ref([]);
fechaColor.value = [
  {color: '#67C6E3'},
  {color: '#A084DC'},
  {color: '#BFACE2'},
  {color: '#EBC7E6'},
  {color: '#E2BBE9'}
];

const educacion = ref([
  {fecha: '2024', title: 'Técnicatura Universitaria en Programacion', descripcion: 'Actualmente estoy cursando una Tecnicatura Universitaria en Programación. Cada día aprendo algo nuevo sobre el mundo de la tecnología y cómo resolver problemas con código. Me encanta descubrir nuevas herramientas y desafíos; estoy en camino de convertirme en programadora y ya estoy construyendo las bases para mi futuro en esta área.', enlace:'https://www.youtube.com/'},
  {fecha: '2023', title: 'Desarrollador Full Stack', descripcion: 'Trabajé en XYZ Tech, donde diseñé y desarrollé aplicaciones web completas utilizando tecnologías como Node.js, React y MongoDB.', enlace:'http:www.direccion.com'},
  {fecha: '2022', title: 'Internship en Desarrollo Web', descripcion: 'Realicé una pasantía en ABC Solutions, contribuyendo en la creación de interfaces de usuario y optimización de sitios web.', enlace:'http:www.direccion.com'},]);
</script>

<template>
  <ul>
    <li v-for="(item, index) in educacion" :key="index" :style="{ '--fecha-color': fechaColor[index].color}">
      <div class="fecha">{{ item.fecha }}</div>
      <h3 class="title">{{ item.title }}</h3>
      <div class="descripcion">{{ item.descripcion }}</div>
      <a class="enlace" :href="item.enlace" target="_blank">Saber más</a>
    </li>
  </ul>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Corben:wght@400;700&family=Mogra&family=Russo+One&family=Signika+Negative:wght@300..700&display=swap');

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  --color: rgba(30, 30, 30);
  --bgColor: rgba(245, 245, 245);
  min-height: 100vh;
  display: grid;
  align-content: center;
  gap: 2rem;
  padding: 2rem;
  font-family: Mogra;
  color: var(--color);
  background: var(--bgColor);
}

ul {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* Cambié a tres columnas */
  gap: 2rem; /* Espacio entre las tarjetas */
  list-style: none;
  width: min(90%, 100rem); /* Limité el ancho máximo */
  margin-inline: auto;
}

ul li {
  display: grid;
  grid-template-rows: repeat(3, min-content);
  padding: 1.5rem;
  background-color: rgba(255, 255, 255, 0.2);
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

ul li:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

ul li > * {
  margin: 0.5rem 0;
  text-align: left;
  color: #E7E9F4;
  font-weight: 500;
}

ul li h3 {
  font-size: 1.25rem;
  color: #67C6E3;
  margin-bottom: 0.3rem;
}

ul li p {
  font-size: 1rem;
  color: #EBC7E6;
}

ul li a {
  font-size: 0.9rem;
  color: #67C6E3;
  text-decoration: none;
  margin-top: 0.5rem;
  transition: color 0.2s ease;
}

ul li a:hover {
  color: #003366;
}

ul li .fecha {
  --dateH: 3rem;
  height: var(--dateH);
  margin-inline: calc(1.5rem * -1);
  text-align: center;
  background-color:#67C6E3;
  color: #E7E9F4;
  font-size: 1.25rem;
  font-weight: 700;
  display: grid;
  place-content: center;
  position: relative;
  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
}
</style>
