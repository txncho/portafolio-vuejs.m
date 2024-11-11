<template>
    <nav class="navbar">
        <div class="navbar-menu">
            <ul class="nav-list">
                <li v-for="nav in navegacion" :key="nav.nombre">
                    <a :href="nav.enlace" class="nav-item button">{{nav.nombre}}</a>
                </li>  
            </ul>
        </div>
    </nav>
</template>

<script setup>
import { ref } from 'vue';
const navegacion = ref([
    { id: 1, nombre: 'Educación', enlace: '#educacion' },
    { id: 2, nombre: 'Experiencia', enlace: '#experiencia' },
    { id: 3, nombre: 'Proyectos', enlace: '#proyectos' },
    { id: 4, nombre: 'Habilidades', enlace: '#habilidades' },
    { id: 5, nombre: 'Intereses', enlace: '#intereses' }
]);
</script>

<style scoped>
/* Efecto de vidrio */
.navbar {
    position: fixed; /* Mantener la navbar fija en la parte superior */
    top: 0; /* Alinea la navbar en la parte superior */
    left: 0; /* Alinea la navbar a la izquierda */
    right: 0; /* Alinea la navbar a la derecha */
    background: rgba(255, 255, 255, 0.2); /* Fondo traslúcido */
    backdrop-filter: blur(10px); /* Efecto de desenfoque */
    color: #fff; /* Establece el color del texto en blanco */
    padding: 1rem 2rem; /* Aumenta el padding de la navbar */
    z-index: 1000; /* Asegura que la navbar esté por encima de otros elementos */
}

.navbar-menu {
    display: flex; /* Organiza los elementos en línea usando flexbox */
    justify-content: flex-end; /* Alinea los elementos al final de la navbar */
}

.nav-list {
    list-style: none; /* Elimina los puntos o números de las listas */
    padding: 0; /* Elimina el padding predeterminado */
    margin: 0; /* Elimina el margen predeterminado */
    display: flex; /* Asegura que los elementos de la lista estén uno al lado del otro */
}

.nav-list li {
    margin-left: 1rem; /* Espaciado entre los elementos de la lista */
}

.button {
    position: relative;
    padding: 8px 16px; /* Ajustar el padding para hacer los botones más pequeños */
    border-radius: 6px; /* Esquinas redondeadas */
    border: none; /* Sin borde */
    color: #fcf1f1; /* Color del texto */
    cursor: pointer; /* Cursor de puntero */
    background-color: #111b1f; /* Color de fondo */
    transition: all 0.2s ease; /* Transición suave */
}

.button:active {
    transform: scale(0.96); /* Efecto al hacer clic */
}

/* Efectos al pasar el ratón */
.button:before,
.button:after {
    position: absolute;
    content: "";
    width: 150%;
    left: 50%;
    height: 100%;
    transform: translateX(-50%);
    z-index: -1000;
    background-repeat: no-repeat;
}

.button:hover:before {
    top: -70%;
    background-image: radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, transparent 20%, #7d2ae8 20%, transparent 30%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, transparent 10%, #7d2ae8 15%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%);
    background-size: 10% 10%, 20% 20%, 15% 15%, 20% 20%, 18% 18%, 10% 10%, 15% 15%, 10% 10%, 18% 18%;
    background-position: 50% 120%;
    animation: greentopBubbles 0.6s ease;
}

/* Animaciones y efectos adicionales */
@keyframes greentopBubbles {
    0% {
        background-position: 5% 90%, 10% 90%, 10% 90%, 15% 90%, 25% 90%, 25% 90%, 40% 90%, 55% 90%, 70% 90%;
    }
    50% {
        background-position: 0% 80%, 0% 20%, 10% 40%, 20% 0%, 30% 30%, 22% 50%, 50% 50%, 65% 20%, 90% 30%;
    }
    100% {
        background-position: 0% 70%, 0% 10%, 10% 30%, 20% -10%, 30% 20%, 22% 40%, 50% 40%, 65% 10%, 90% 20%;
        background-size: 0% 0%, 0% 0%, 0% 0%, 0% 0%, 0% 0%, 0% 0%;
    }
}

.button:hover::after {
    bottom: -70%;
    background-image: radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, transparent 10%, #7d2ae8 15%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%),
                      radial-gradient(circle, #7d2ae8 20%, transparent 20%);
    background-size: 15% 15%, 20% 20%, 18% 18%, 20% 20%, 15% 15%, 20% 20%, 18% 18%;
    background-position: 50% 0%;
    animation: greenbottomBubbles 0.6s ease;
}

@keyframes greenbottomBubbles {
    0% {
        background-position: 10% -10%, 30% 10%, 55% -10%, 70% -10%, 85% -10%, 70% -10%, 70% 0%;
    }
    50% {
        background-position: 0% 80%, 20% 80%, 45% 60%, 60% 100%, 75% 70%, 95% 60%, 105% 0%;
    }
    100% {
        background-position: 0% 90%, 20% 90%, 45% 70%, 60% 110%, 75% 80%, 95% 70%, 110% 10%;
        background-size: 0% 0%, 0% 0%, 0% 0%, 0% 0%, 0% 0%;
    }
}
</style>
