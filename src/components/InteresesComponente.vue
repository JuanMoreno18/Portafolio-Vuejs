<script setup>
import { ref } from 'vue';
import FondoLava from './FondoLava.vue';

//Liste es un arreglo con ref para que se pueda reactivar el cambio de los intereses
const intereses = ref([
    'Desarrollo de Software de Código Abierto: Contribuyo a proyectos en GitHub, colaborando con otros desarrolladores para mejorar herramientas y librerías.',
    'Deportes al Aire Libre: Disfruto del senderismo y el ciclismo de montaña, actividades que practico regularmente para mantener un equilibrio entre el trabajo y la salud física.',
    'Tecnología de Innovación: Me apasiona explorar nuevas tendencias tecnológicas como la inteligencia artificial y el desarrollo de aplicaciones móviles.',
    'Fotografía: Practico la fotografía como un hobby, lo que me ayuda a mantener una perspectiva creativa tanto en mi vida profesional como personal.'
]);
</script>

<template>
  <div class="intereses-contenedor">
    <!-- Fondo animado -->
    <FondoLava />

    <!-- Contenido encima del fondo -->
    <ul class="contenedor-lista">
      <li class="item" v-for="interes in intereses" :key="interes">
        {{ interes }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
.intereses-contenedor {
  position: relative; /* Necesario para posicionar el fondo */
  display: flex;
  flex-direction: column; /* o row si querés texto al costado */
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  max-width: 85%;
  padding: 2rem;
  min-height: 100vh; /* hace que ocupe toda la pantalla */
  overflow: hidden; /* evita que el fondo sobresalga */
}

.intereses-contenedor :deep(.fondo-lava) {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 0; /* queda detrás */
}

.contenedor-lista {
  position: relative; /* el texto queda encima del fondo */
  z-index: 1;
  list-style-type: none;
  padding: 1rem;
  margin-bottom: 0.5rem;
  color: var(--vt-c-white-soft);
  font-size: 1.4rem;
  text-shadow: 3px 3px 6px rgba(0, 0, 0, 1);
}

.item {
  margin-bottom: 1rem;
}
</style>