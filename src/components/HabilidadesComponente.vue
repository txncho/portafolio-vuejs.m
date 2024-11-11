<script setup>
import img1 from '/src/components/icons/js.svg';
import img2 from '/src/components/icons/python.svg';
import img3 from '/src/components/icons/html-css.svg';
import img4 from '/src/components/icons/java.svg';
import img5 from '/src/components/icons/sql.svg';
import img6 from '/src/components/icons/react.svg';
import img7 from '/src/components/icons/vue.svg';
import img8 from '/src/components/icons/node.svg';
import img11 from '/src/components/icons/git.svg';
import img14 from '/src/components/icons/figma.svg';
import img15 from '/src/components/icons/visual.svg';
import img17 from '/src/components/icons/mysql.svg';
import img18 from '/src/components/icons/postgres.svg';
import img19 from '/src/components/icons/arg.svg';
import img20 from '/src/components/icons/eeuu.svg';

import { ref } from 'vue';

const habilidades = ref([
    {
        id: 1, nombre: 'Lenguajes de Programación', habilidades: [
            { id: 1, nombre: 'JavaScript', nivel: 'Avanzado', icono: img1 },
            { id: 2, nombre: 'Python', nivel: 'Avanzado', icono: img2 },
            { id: 3, nombre: 'HTML/CSS', nivel: 'Avanzado', icono: img3 },
            { id: 4, nombre: 'Java', nivel: 'Avanzado', icono: img4 },
            { id: 5, nombre: 'SQL', nivel: 'Intermedio', icono: img5 }
        ]
    },
    {
        id: 2, nombre: 'Frameworks y Librerías', habilidades: [
            { id: 1, nombre: 'React.js', nivel: 'Avanzado', icono: img6 },
            { id: 2, nombre: 'Vue.js', nivel: 'Intermedio', icono: img7 },
            { id: 3, nombre: 'Node.js', nivel: 'Avanzado', icono: img8 },
        ]
    },
    {
        id: 3, nombre: 'Herramientas y Software', habilidades: [
            { id: 1, nombre: 'Git', nivel: 'Avanzado', icono: img11 },
            { id: 4, nombre: 'Figma', nivel: "Avanzado", icono: img14 },
            { id: 5, nombre: 'Visual Studio Code', nivel: 'Avanzado', icono: img15 }
        ]
    },
    {
        id: 4, nombre: 'Bases de Datos', habilidades: [
            { id: 2, nombre: 'MySQL', nivel: 'Avanzado', icono: img17 },
            { id: 3, nombre: 'PostgreSQL', nivel: 'Avanzado', icono: img18 }
        ]
    },
    {
        id: 5, nombre: 'Idiomas', habilidades: [
            { id: 1, nombre: 'Español', nivel: 'Nativo', icono: img19 },
            { id: 2, nombre: 'Inglés', nivel: 'Intermedio', icono: img20 }
        ]
    }
]);
</script>

<template>
    <div class="skills-contenedor">
        <div v-for="categoria in habilidades" :key="categoria.id" class="skills-categoria">
            <h3>{{ categoria.nombre }}</h3>
            <ul class="skills">
                <li v-for="habilidad in categoria.habilidades" :key="habilidad.id" class="skill">
                    <img :src="habilidad.icono" :alt="habilidad.nombre" />
                    <span>{{ habilidad.nombre }}: {{ habilidad.nivel }}</span>
                </li>
            </ul>
        </div>
    </div>
</template>

<style scoped>
.skills-contenedor {
    padding: 2rem;
    background: #704c6f;
    border-radius: 20px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.skills-categoria {
    margin-bottom: 20px;
    border-bottom: 2px solid rgba(0, 0, 0, 0.1);
    padding-bottom: 15px;
}

.skills-categoria h3 {
    margin-bottom: 10px;
    font-size: 1.8em;
    color: #67c6e3;
    font-weight: bold;
    text-align: center;
}

.skills {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 15px;
}

.skill {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    background-color: rgba(255, 255, 255, 0.1); /* Fondo transparente */
    padding: 0.5em 1em;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(10px); /* Desenfoque de fondo para simular vidrio */
    transition: transform 0.3s, box-shadow 0.3s, border 0.3s;
    flex: 1 1 150px;
    border: 1px solid rgba(0, 0, 0, 0.1); /* Borde sutil */
}

.skill:hover {
    transform: translateY(-5px);
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.2);
    background-color: rgba(244, 244, 244, 0.2); /* Cambiar color de fondo al pasar el ratón */
    border: 2px solid #c889c7; /* Resaltar borde en hover */
}

.skill img {
    width: 40px;
    height: 40px;
}

.skill span {
    font-size: 1em;
    color: #333;
    font-weight: 500;
}

@media (max-width: 768px) {
    .skills-categoria h3 {
        font-size: 1.5em;
    }

    .skill {
        flex: 1 1 100px; /* Reducir tamaño en pantallas pequeñas */
    }
}
</style>
