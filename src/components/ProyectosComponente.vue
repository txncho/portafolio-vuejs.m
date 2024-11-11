<script setup>
import proyecto1 from '/src/assets/fotohotel.png';
import proyecto2 from '/src/assets/anime1.webp';
import proyecto3 from '/src/assets/anime2.jpg';
import proyecto4 from '/src/assets/fotohotel2.png';

import { ref } from 'vue';
var misProyectos = ref([
    {
        id: 1,
        src: proyecto1,
        titulo: "Aplicación de Reservas para Hoteles",
        descripcion: "Creé una aplicación móvil que permite a los usuarios reservar habitaciones en htoeles locales.",
        projectoLink: "https://www.google.com.ar",
        githubLink: "https://github.com/usuario/proyecto"
    },
    {
        id: 2,
        src: proyecto2,
        titulo: "Plataforma de Streaming anime (2022)",
        descripcion: "Diseñé y desarrollé una plataforma de streaming en línea utilizando Django y React. Con diferentes funcionalidades.",
        projectoLink: "https://www.google.com.ar",
        githubLink: "https://github.com/usuario/proyecto"
    },
    {
        id: 3,
        src: proyecto3,
        titulo: "PLataforma de Streaming anime paga",
        descripcion: "Construí una plataforma con un sistema de gestión de pagos para transmitir series y peliculas.",
        projectoLink: "https://www.google.com.ar",
        githubLink: "https://github.com/usuario/proyecto"
    },
    {
        id: 4,
        src: proyecto4,
        titulo: "Aplicación de Reservas para Hoteles (2023)",
        descripcion: "Creé una aplicación móvil que permite a los usuarios reservar habitaciones en hoteles locales.",
        projectoLink: "https://www.google.com.ar",
        githubLink: "https://github.com/usuario/proyecto"
    },
]);
</script>

<template>
    <div class="galeria">
        <ul>
            <li class="proyecto" v-for="proyecto in misProyectos" :key="proyecto.id">
                <img :src="proyecto.src" :alt="proyecto.titulo">
                <div class="proyecto-info">
                    <h3>{{ proyecto.titulo }}</h3>
                    <p>{{ proyecto.descripcion }}</p>
                    <div class="proyecto-links">
                        <a :href="proyecto.projectoLink" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Proyecto</a>
                        <a :href="proyecto.githubLink" class="github-link" target="_blank" rel="noopener noreferrer">Ver Código en GitHub</a>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.galeria {
    width: 100%;
    padding: 15px; /* Aumentar el padding para un fondo más ancho */
    background: linear-gradient(-45deg, #021526, #03346E, #6EACDA, #E2E2B6);
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
}

@keyframes gradient {
    0% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 50%;
    }
    100% {
        background-position: 0% 50%;
    }
}

ul {
    list-style-type: none; /* Eliminar viñetas de la lista */
    padding: 0; /* Eliminar padding de la lista */
    display: flex; /* Usar flexbox para disposición horizontal */
    flex-wrap: wrap; /* Permitir que los elementos se envuelvan */
    justify-content: center; /* Centrar elementos horizontalmente */
}

.proyecto {
    display: flex;
    flex-direction: column;
    border: 2px solid #ddd;
    border-radius: 12px;
    overflow: hidden;
    background-color: rgba(255, 255, 255, 0.85); /* Fondo más tranquilo y claro para las tarjetas */
    max-width: 380px; /* Aumentar el ancho máximo de las tarjetas */
    margin: 15px; /* Margen entre proyectos */
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); /* Sombra sutil */
    transition: transform 0.3s, box-shadow 0.3s; /* Transición suave */
}

.proyecto:hover {
    transform: translateY(-5px); /* Elevar al pasar el mouse */
    box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2); /* Aumentar sombra al pasar el mouse */
}

.proyecto img {
    width: 100%;
    height: auto;
    display: block;
}

.proyecto-info {
    padding: 15px;
    text-align: center;
}

.proyecto-info h3 {
    margin: 10px 0;
    font-size: 1.5em; /* Aumentar tamaño del título */
    color: #67C6E3;
}

.proyecto-info p {
    margin: 10px 0;
    font-size: 1em;
    color: #3c3c3c;
}

.proyecto-links {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 20px; /* Ajustar margen superior */
}

.proyecto-links .btn-ver-mas {
    background-color: #c889c7;
    color: #fff;
    padding: 10px 15px;
    border-radius: 5px;
    text-decoration: none;
    transition: background-color 0.3s;
}

.proyecto-links .btn-ver-mas:hover {
    background-color: #9b739a; /* Azul más oscuro */
}

.proyecto-links .github-link {
    color: #3c3c3c;
    text-decoration: none;
    font-size: 0.9em;
}

.proyecto-links .github-link:hover {
    text-decoration: underline; /* Subrayar al pasar el mouse */
}
</style>
