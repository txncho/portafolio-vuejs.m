<script setup>
import { ref } from 'vue';
// Este es un arreglo con ref para que se pueda reactivar el cambio de los intereses
const intereses = ref([
    'Me encanta aprender nuevas tecnologías, ya que siempre estoy en busca de herramientas innovadoras que mejoren mis habilidades y expandan mis conocimientos. Me motiva estar al tanto de las últimas tendencias para seguir creciendo como profesional.',
    'Me apasionan los videojuegos, ya que combinan creatividad, desafío y tecnología. Disfruto explorar nuevas experiencias y aprender sobre el diseño y desarrollo que hacen posible este entretenimiento interactivo',
    'Me encanta el desarrollo frontend porque me permite combinar creatividad y tecnología para crear interfaces atractivas y funcionales. Disfruto diseñar experiencias de usuario intuitivas y visualmente agradables.',
    'Me apasiona el desarrollo backend, ya que me permite construir la lógica y la infraestructura que hacen posible aplicaciones robustas y escalables. Disfruto trabajando con bases de datos, servidores y optimizando el rendimiento.'
]);
</script>

<template>
    <div class="intereses-contenedor">
        <FondoLava />
        <ul class="contenedor-lista">
            <li class="item" v-for="interes in intereses" :key="interes">
                {{ interes }}
            </li>
        </ul>
    </div>
</template>

<style scoped>
.intereses-contenedor {
    display: flex;
    flex-direction: column; /* Para que los elementos se apilen verticalmente */
    align-items: center; /* Centra la lista horizontalmente */
    position: relative;
    margin: 0 auto;
    max-width: 85%;
    padding: 2rem; /* Espaciado interior más amplio */
    background: rgba(255, 255, 255, 0.1); /* Fondo transparente con color blanco */
    border-radius: 12px; /* Bordes redondeados */
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1); /* Sombra suave */
}

.contenedor-lista {
    list-style-type: none;
    padding: 0; /* Elimina el padding de la lista */
    margin: 0; /* Elimina el margen de la lista */
    color: #D9E0E8; /* Color de texto oscuro */
    font-size: 1.2rem; /* Tamaño de fuente más pequeño y elegante */
}

.item {
    margin-bottom: 1rem;
    padding: 1rem; /* Espaciado alrededor de cada ítem */
    background: rgba(106, 199, 227, 0.2); /* Fondo celeste semi-transparente */
    border: 1px solid #e1e1e1; /* Borde sutil alrededor de cada ítem */
    border-radius: 8px; /* Bordes redondeados para cada ítem */
    transition: none; /* Sin efecto de hover */
}
</style>
