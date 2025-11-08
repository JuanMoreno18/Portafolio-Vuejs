<script setup>
import { ref } from 'vue';
import FondoLava from './FondoLava.vue';

//Liste es un arreglo con ref para que se pueda reactivar el cambio de los intereses
const intereses = ref([
    'Actualmente curso la carrera de Programación en la UTN, donde llevo un año fortaleciendo mis conocimientos en desarrollo de software, lógica y resolución de problemas. Me motiva seguir aprendiendo y aplicar lo que estudio en proyectos reales',
    'Además de la programación, me apasiona el diseño gráfico. Disfruto crear interfaces limpias y visualmente atractivas, buscando siempre combinar funcionalidad y estética en cada proyecto.',
    'Tengo gran facilidad para la informática y la tecnología en general. Me gusta explorar nuevas herramientas, optimizar procesos y mantenerme actualizado con las últimas tendencias del sector.',
    'Valoro el trabajo en equipo y la oportunidad de colaborar con otros desarrolladores. Considero que cada proyecto es una oportunidad para aprender, compartir ideas y mejorar como profesional.'
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
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  max-width: 100%;
  padding: 3rem 2rem;
  min-height: 100vh;
  overflow: hidden;
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