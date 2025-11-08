<script setup>

import NavBar from './components/icons/NavBar.vue';
import DatosPersonales from './components/DatosPersonales.vue';
import Educacion from './components/EducacionComponente.vue';
import ExperienciaComponente from './components/ExperienciaComponente.vue';
import ProyectosComponente from './components/ProyectosComponente.vue';
import HabilidadesComponente from './components/HabilidadesComponente.vue';
import InteresesComponente from './components/InteresesComponente.vue';
</script>

<template>
  <header id="aTop">
     <!-- barra de navegacion -->
    <NavBar />
    <!-- componente Datos peronales -->
     <DatosPersonales />
    
  </header>
  <main>
      <section id="Educacion"><h2>Educacion - Cursos</h2><Educacion /></section>
      <section id="experiencia"><h2>Experiencia</h2><ExperienciaComponente /></section>
      <section id="proyectos"><h2>Proyectos</h2><ProyectosComponente /></section>
      <section id="habilidades"><h2>Habilidades</h2><HabilidadesComponente /></section>
      <section id="intereses"><h2>Intereses</h2><InteresesComponente /></section>


  </main>
  <footer>
        <a href="#aTop" class="footer-link">↑ Volver al inicio</a>
        <p class="footer-text">© 2025 Juan Moreno - Portafolio web</p>
      </footer>

</template>
<style>
body {
  margin: 0;
  padding: 0;
  min-height: 100vh;
  background-color: #000810;
  position: relative;
}

body::before {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('@/assets/fondogris.avif');
  background-size: cover; /* ✅ Hace que la imagen cubra toda la pantalla */
  background-position: center; /* ✅ Centra la imagen */
  background-attachment: fixed;
  background-repeat: no-repeat; /* Para que se repita como mosaico */
  opacity: 0.4;
  pointer-events: none;
  z-index: -1;
}
</style>

<style scoped>

footer {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 3rem 2rem;
  margin-top: 4rem;
  background: rgba(10, 14, 39, 0.6);
  backdrop-filter: blur(10px);
  border-top: 1px solid rgba(167, 139, 250, 0.2);
}

.footer-link {
  font-size: 1.2rem;
  color: #a78bfa;
  text-decoration: none;
  padding: 0.8rem 2rem;
  border: 2px solid #a78bfa;
  border-radius: 30px;
  margin-bottom: 1.5rem;
  transition: all 0.3s ease;
  font-weight: 600;
}

.footer-link:hover {
  background: #a78bfa;
  color: #0a0e27;
  box-shadow: 0 0 30px rgba(167, 139, 250, 0.5);
  transform: translateY(-3px);
}

.footer-text {
  font-size: 1.1rem;
  color: rgba(255, 255, 255, 0.7);
  margin: 0;
}

</style>
