<script setup>
import {ref} from 'vue';
const titulo= "Desarrollador full stack";
const fecha= "Desde enero 2023 / Julio 2024";
const experiencias = ref([
    {id:1, src: '/src/assets/ventas.svg', parrafo: 'Lideré un equipo de 5 desarrolladores en la creación de una plataforma de comercio electrónico que incrementó las ventas en un 35% durante el primer año.'},
  {id:2, src: '/src/assets/ecommerce.svg', parrafo: 'Diseñé y desarrollé aplicaciones web utilizando Node.js, React y MongoDB, logrando reducir el tiempo de carga de las páginas en un 50%.'},
  {id:3, src: '/src/assets/configuracion.svg', parrafo: 'Implementé soluciones de autenticación y autorización, mejorando la seguridad del sitio web y reduciendo los intentos de acceso no autorizado en un 20%.'},
  {id:4, src: '/src/assets/uiux.svg', parrafo: 'Colaboré con diseñadores de UX/UI para crear interfaces de usuario atractivas y fáciles de usar, aumentando la satisfacción del cliente en un 15%.'},
  {id:5, src: '/src/assets/watch.svg', parrafo: 'Automaticé procesos de despliegue continuo utilizando Jenkins y Docker, reduciendo los tiempos de despliegue en un 40%.'}
]);
</script>
<template>
  <div class="card">
    <h3 class="titulo">{{ titulo }}</h3>
    <p class="fecha">{{ fecha }}</p>
    <ul class="listado">
      <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
        <img class="imagen-svg" :src="experiencia.src" width="45rem" :alt="experiencia.parrafo">
        <p>{{ experiencia.parrafo }}</p>
      <!-- </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/ventas.svg" width="45rem" alt="">
        <p>Lideré un equipo de 5 desarrolladores en la creación de una plataforma de comercio electrónico que incrementó las ventas en un 35% durante el primer año.</p>
      </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/ecommerce.svg" width="45rem" alt="">
        <p>Diseñé y desarrollé aplicaciones web utilizando Node.js, React y MongoDB, logrando reducir el tiempo de carga de las páginas en un 50%.</p>
      </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/configuracion.svg" width="45rem" alt="">
        <p>Implementé soluciones de autenticación y autorización mejorando la seguridad del sitio web y reduciendo los intentos de acceso no autorizado en un 20%.</p>
      </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/ux.svg" width="45rem" alt="">
        <p>Colaboré con diseñadores de UX/UI para crear interfaces de usuario atractivas y fáciles de usar, aumentando la satisfacción del cliente en un 15%.</p>
      </li>
      <li class="item"><img class="imagen-svg" src="/src/assets/watch.svg" width="45rem" alt="">
        <p>Automaticé procesos de despliegue continuo utilizando Jenkins y Docker, reduciendo los tiempos de despliegue en un 40%.</p> -->
      </li>
    </ul>
  </div>
</template>

<style scoped>
.card{
  display: flex;
  flex-direction: column;
  padding: 2.5rem;
  background: linear-gradient(135deg, #1a2332 0%, #253241 100%);
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid rgba(99, 179, 237, 0.1);
}

.card:hover{
  transform: translateY(-5px);
  box-shadow: 0 15px 40px rgba(59, 130, 246, 0.2);
}

.titulo{
  font-size: 2rem;
  font-weight: 700;
  color: #60a5fa;
  margin-bottom: 0.5rem;
  text-transform: capitalize;
  letter-spacing: 0.5px;
}

.fecha{
  font-size: 1rem;
  color: #93c5fd;
  margin-bottom: 2rem;
  opacity: 0.85;
  font-weight: 400;
}

.listado{
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
  list-style: none;
  padding: 0;
  margin: 0;
}

.item{
  display: flex;
  align-items: center;
  padding: 1.5rem;
  gap: 1.5rem;
  background: rgba(255, 255, 255, 0.03);
  border-radius: 15px;
  border: 1px solid rgba(96, 165, 250, 0.15);
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
}

.item:hover{
  background: rgba(96, 165, 250, 0.08);
  border-color: rgba(96, 165, 250, 0.3);
  transform: translateX(8px);
  box-shadow: 0 5px 20px rgba(96, 165, 250, 0.15);
}

.icon-wrapper{
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 65px;
  height: 65px;
  background: linear-gradient(135deg, rgba(96, 165, 250, 0.15), rgba(59, 130, 246, 0.1));
  border-radius: 14px;
  padding: 0.5rem;
  transition: transform 0.3s ease;
  border: 1px solid rgba(96, 165, 250, 0.2);
}

.item:hover .icon-wrapper{
  transform: scale(1.08);
  background: linear-gradient(135deg, rgba(96, 165, 250, 0.2), rgba(59, 130, 246, 0.15));
}

.imagen-svg{
  width: 45px;
  height: 45px;
  filter: brightness(1.1) drop-shadow(0 2px 4px rgba(0, 0, 0, 0.2));
}

.parrafo{
  color: #e2e8f0;
  line-height: 1.7;
  font-size: 1rem;
  margin: 0;
  font-weight: 400;
}
</style>