<script setup>
import {ref} from 'vue';
const titulo= "Programador y Técnico en Tecnología";
const fecha= "Desde enero 2018 /  Noviembre 2025";
const experiencias = ref([
  {id:1, src: '/src/assets/ventas.svg', titulo: 'Trabajo en Equipo', parrafo: 'Trabajo en equipo con siete compañeros desarrollando proyectos de la tecnicatura en programacion. Me destaco por mi comunicación, compromiso y colaboración constante. Disfruto aprender y aportar ideas en cada etapa del desarrollo..'},
  {id:2, src: '/src/assets/ecommerce.svg', titulo: 'Desarrollo Web', parrafo: 'Diseñé y desarrollé aplicaciones web utilizando Vue.js, HTML, CSS, JavaScript logrando reducir el tiempo de carga de las páginas en un 50%.'},
  {id:3, src: '/src/assets/configuracion.svg', titulo: 'Optimizar', parrafo: 'Experiencia en reparación de equipos, mantenimiento de sistemas e instalación de software. Me motiva encontrar soluciones eficientes y aprender constantemente.'},
  {id:4, src: '/src/assets/uiux.svg', titulo: 'Inteligencia artificial', parrafo: 'He diseñado proyectos que integran inteligencia artificial para resolver problemas de manera innovadora. Me interesa combinar la creatividad, el desarrollo de software y la IA para crear soluciones útiles y eficientes.'},
]);
</script>
<template>
  <div class="experiencia-container">
    <div class="header-card">
      <div class="header-content">
        <h3 class="titulo">{{ titulo }}</h3>
        <p class="fecha">{{ fecha }}</p>
      </div>
    </div>
    
    <div class="grid-experiencias">
      <div class="experiencia-card" v-for="experiencia in experiencias" :key="experiencia.id">
        <div class="card-header">
          <div class="icon-container">
            <img class="imagen-svg" :src="experiencia.src" :alt="experiencia.titulo">
          </div>
          <h4 class="card-titulo">{{ experiencia.titulo }}</h4>
        </div>
        <div class="card-body">
          <p class="card-parrafo">{{ experiencia.parrafo }}</p>
        </div>
        <div class="card-footer">
          <div class="progress-indicator"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.experiencia-container {
  width: 100%;
  max-width: 1400px;
  margin: 0 auto;
  padding: 2rem;
}

/* Header Card */
.header-card {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 20px;
  padding: 2.5rem;
  margin-bottom: 3rem;
  box-shadow: 0 20px 60px rgba(102, 126, 234, 0.3);
  position: relative;
  overflow: hidden;
}

.header-card::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -20%;
  width: 300px;
  height: 300px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  filter: blur(60px);
}

.header-content {
  position: relative;
  z-index: 1;
  text-align: center;
}

.titulo {
  font-size: 2.8rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 0.8rem;
  text-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
  letter-spacing: 0.5px;
}

.fecha {
  font-size: 1.2rem;
  color: rgba(255, 255, 255, 0.9);
  margin: 0;
  font-weight: 400;
}

/* Grid de Experiencias */
.grid-experiencias {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

/* Tarjetas de Experiencia */
.experiencia-card {
  background: linear-gradient(145deg, #1e2a35 0%, #2c3e50 100%);
  border-radius: 20px;
  padding: 2rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  position: relative;
  overflow: hidden;
}

.experiencia-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 4px;
  background: linear-gradient(90deg, #667eea, #764ba2, #f093fb);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.experiencia-card:hover::before {
  opacity: 1;
}

.experiencia-card:hover {
  transform: translateY(-10px) scale(1.02);
  box-shadow: 0 20px 50px rgba(102, 126, 234, 0.4);
  border-color: rgba(102, 126, 234, 0.5);
}

/* Header de la tarjeta */
.card-header {
  display: flex;
  align-items: center;
  gap: 1.2rem;
  margin-bottom: 1.5rem;
  padding-bottom: 1.2rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.icon-container {
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 60px;
  height: 60px;
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.2), rgba(118, 75, 162, 0.2));
  border-radius: 15px;
  padding: 0.8rem;
  transition: all 0.3s ease;
  border: 1px solid rgba(102, 126, 234, 0.3);
}

.experiencia-card:hover .icon-container {
  transform: rotate(360deg) scale(1.1);
  background: linear-gradient(135deg, rgba(102, 126, 234, 0.4), rgba(118, 75, 162, 0.3));
  box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4);
}

.imagen-svg {
  width: 35px;
  height: 35px;
  filter: brightness(1.2) drop-shadow(0 2px 8px rgba(102, 126, 234, 0.5));
}

.card-titulo {
  font-size: 1.4rem;
  font-weight: 600;
  color: #a78bfa;
  margin: 0;
  letter-spacing: 0.3px;
}

/* Body de la tarjeta */
.card-body {
  margin-bottom: 1.5rem;
}

.card-parrafo {
  color: #e2e8f0;
  line-height: 1.7;
  font-size: 1rem;
  margin: 0;
  font-weight: 400;
}

/* Footer de la tarjeta */
.card-footer {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  margin-top: auto;
}

.progress-indicator {
  flex: 1;
  height: 3px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  position: relative;
  overflow: hidden;
}

.progress-indicator::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 0%;
  background: linear-gradient(90deg, #667eea, #764ba2);
  border-radius: 10px;
  transition: width 0.6s ease;
}

.experiencia-card:hover .progress-indicator::after {
  width: 100%;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .grid-experiencias {
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }
}

@media (max-width: 768px) {
  .experiencia-container {
    padding: 1.5rem;
  }

  .header-card {
    padding: 2rem;
    margin-bottom: 2rem;
  }

  .titulo {
    font-size: 2rem;
  }

  .fecha {
    font-size: 1rem;
  }

  .grid-experiencias {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .experiencia-card {
    padding: 1.5rem;
  }

  .card-titulo {
    font-size: 1.2rem;
  }

  .card-parrafo {
    font-size: 0.95rem;
  }
}

@media (max-width: 480px) {
  .titulo {
    font-size: 1.6rem;
  }

  .icon-container {
    min-width: 50px;
    height: 50px;
  }

  .imagen-svg {
    width: 30px;
    height: 30px;
  }
}
</style>