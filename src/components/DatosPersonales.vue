<script setup>
import linkedin from '/src/assets/linkedin_icon.svg';
import instagram from '/src/assets/instagram_icon.svg';
import github from '/src/assets/github_icon.svg';
import cv from '/src/assets/cv_resume_icon.svg';

const title = 'Juan Martin Fernandez';
const descripcion = 'Técnica Universitaria en Programación - UTN';
const residencia = 'San Rafael, Mendoza, Argentina';
const presentacion = '¡Bienvenidas a mi portafolio! Soy programador y en esta página podrás ver lo que he estado haciendo, los lenguajes y herramientas en los que me especializo.';
const redesSociales = [
  { id: 1, name: 'linkedin', src: linkedin, url: '' },
  { id: 2, name: 'instagram', src: instagram, url: '' },
  { id: 3, name: 'github', src: github, url: '' },
  { id: 4, name: 'curriculum', src: cv, url: '' },
];
const telefono = '+54 9 2604-814477';
</script>

<template>
  <section class="datos-personales">
    <h1 class="nombre">{{ title }}</h1>
    <div class="card">
      <h2>{{ descripcion }}</h2>
      <p>{{ presentacion }}</p>
      <ul class="example-2">
        <li class="icon-content" v-for="red in redesSociales" :key="red.id">
          <a :href="red.url" :data-social="red.name" aria-label="red.name">
            <div class="filled"></div>
            <img class="icon-redsocial" :src="red.src" width="25" :alt="red.name" />
          </a>
        </li>
      </ul>
      <h3>☎ Mi Teléfono personal: {{ telefono }}</h3>
      <h4>{{ residencia }}</h4>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Corben:wght@400;700&family=Mogra&family=Russo+One&family=Signika+Negative:wght@300..700&display=swap');

/* Paleta de colores */
.datos-personales {
  --color-primary: #bdbdd1;   /* Azul oscuro suave */
  --color-secondary: #0a2222; /* Morado pastel */
  --color-tertiary: #c8d8dd;  /* Lavanda claro */
  --color-quaternary: #67C6E3; /* Rosa pastel */
  --color-accent: #A3D8FF;    /* Fondo claro */
}

body {
  background-color: var(--color-secondary);
  color: var(--color-accent);
  font-family: 'Signika Negative', sans-serif;
}

/* Título del nombre */
.nombre {
  text-align: center;
  font-size: 3.5rem;
  font-family: 'Signika Negative', sans-serif;
  color: var(--color-quaternary);
  margin-bottom: 15px;
  text-shadow: 1px 1px 6px rgba(0, 0, 0, 0.3);
}

/* Tarjeta principal */
.card {
  backdrop-filter: blur(10px);
  border-radius: 20px;
  padding: 25px;
  margin: 0 auto;
  max-width: 750px;
  text-align: center;
  color: var(--color-accent);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3);
}

/* Subtítulos */
h2 {
  font-size: 2rem;
  color: var(--color-tertiary);
}

p {
  font-size: 1.15rem;
  margin-bottom: 1.5rem;
}

h3, h4 {
  font-size: 1rem;
  color: #e5eaf5;
}

/* Iconos de redes sociales */
.example-2 {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 15px;
}

.icon-content a {
  position: relative;
  width: 55px;
  height: 55px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: var(--color-primary);
  background-color: #ffffff;
  transition: box-shadow 0.3s ease-in-out;
}

.icon-content a:hover {
  box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.2);
}

.icon-content a img {
  width: 30px;
  height: 30px;
  position: relative;
  z-index: 1;
}

.icon-content a .filled {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 0;
  border-radius: 50%; /* Hace el efecto redondeado */
  background-color: var(--color-tertiary);
  transition: height 0.3s ease-in-out;
}

.icon-content a:hover .filled {
  height: 100%;
}

/* Colores específicos de cada red social */
.icon-content a[data-social="linkedin"] .filled {
  background-color: #0077B5;
}

.icon-content a[data-social="github"] .filled {
  background-color: #333;
}

.icon-content a[data-social="instagram"] .filled {
  background: linear-gradient(45deg, #833AB4, #FD1D1D, #F77737);
}

.icon-content a[data-social="curriculum"] .filled {
  background-color: var(--color-primary);
}
</style>
