<script setup>
import icono1 from '/src/assets/ventas.svg';
import icono2 from '/src/assets/ecomerce.svg';
import icono3 from '/src/assets/configuracion.svg';
import icono4 from '/src/assets/uiux.svg';
import icono5 from '/src/assets/watch.svg';

import { ref } from 'vue';
const titulo = 'Desarrollador Full Stack';
const experiencias = ref([
    { id: 1, src: icono1, parrafo: 'Lideré un equipo de 5 desarrolladores en la creación de una plataforma de comercio electrónico que incrementó las ventas en un 35% durante el primer año.' },
    { id: 2, src: icono2, parrafo: 'Diseñé y desarrollé aplicaciones web utilizando Node.js, React y MongoDB, logrando reducir el tiempo de carga de las páginas en un 50%.' },
    { id: 3, src: icono3, parrafo: 'Implementé soluciones de autenticación y autorización, mejorando la seguridad del sitio web y reduciendo los intentos de acceso no autorizado en un 20%.' },
    { id: 4, src: icono4, parrafo: 'Colaboré con diseñadores de UX/UI para crear interfaces de usuario atractivas y fáciles de usar, aumentando la satisfacción del cliente en un 15%.' },
    { id: 5, src: icono5, parrafo: 'Automaticé procesos de despliegue continuo utilizando Jenkins y Docker, reduciendo los tiempos de despliegue en un 40%.' },
]);
</script>

<template>
    <div class="card">
        <h3 class="titulo">{{ titulo.toLocaleUpperCase() }}</h3>
        <p class="fecha">{{ fecha }}</p>
        <ul class="listado">
            <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
                <img class="imagen-svg" :src="experiencia.src" width="45rem" :alt="experiencia.parrafo">
                <p class="descripcion">{{ experiencia.parrafo }}</p>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    padding: 2rem;
    background: linear-gradient(to bottom right, rgba(40, 58, 73, 0.8), rgba(28, 41, 52, 0.8));
    border-radius: 15px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
    backdrop-filter: blur(10px);
}

.titulo {
    font-size: 1.8rem; /* Aumentar el tamaño del título */
    color: #67C6E3;
    text-align: center; /* Centrar el título */
    margin-bottom: 0.5rem; /* Espaciado inferior */
}

.listado {
    display: flex;
    flex-direction: column;
    gap: 1rem; /* Espaciado entre los items */
}

.item {
    align-items: center;
    display: flex;
    padding: 1rem;
    gap: 1.5rem;
    background-color: rgba(255, 255, 255, 0.1); /* Fondo para los items */
    border-radius: 10px; /* Bordes redondeados */
    transition: transform 0.3s; /* Transición al pasar el mouse */
}

.item:hover {
    transform: translateY(-5px); /* Efecto al pasar el mouse */
    background-color: rgba(255, 255, 255, 0.2); /* Cambio de fondo al pasar el mouse */
}

.descripcion {
    color: #fff; /* Color del texto de la descripción */
    font-size: 1rem; /* Tamaño de la fuente de la descripción */
    line-height: 1.5; /* Espaciado entre líneas */
}
</style>
