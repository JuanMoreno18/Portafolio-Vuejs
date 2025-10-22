<script setup>

import { ref } from 'vue';
const fechaColor = ref([]);
/*Esta es otra forma de utilizar el arreglo, con el metodo value*/
fechaColor.value = [
  {color: '#41516c'},
  {color: '#FBCA3E'},
  {color: '#E24A68'},
  {color: '#1B5F8C'},
  {color: '#4CADAD'}
];
/*Esta es la forma de utilizar el arreglo, sin el metodo value*/
const educacion = ref([
  {fecha: '2024', title: 'Técnicatura Universitaria en Programacion', descripcion: 'Incumbencias Profesionales: Operación y programación de computadoras, desarrollo de programas en distintos lenguajes, análisis y control de sistemas informáticos.', enlace:'https://www.youtube.com/'},
  {fecha: '2023', title: 'Desarrollador Full Stack', descripcion: 'Trabajé en XYZ Tech, donde diseñé y desarrollé aplicaciones web completas utilizando tecnologías como Node.js, React y MongoDB.', enlace:'http:www.direccion.com'},
  {fecha: '2022', title: 'Internship en Desarrollo Web', descripcion: 'Realicé una pasantía en ABC Solutions, contribuyendo en la creación de interfaces de usuario y optimización de sitios web.', enlace:'http:www.direccion.com'},
  {fecha: '2021', title: 'Proyecto Personal - Aplicación de Gestión de Tareas', descripcion: 'Desarrollé una aplicación para la gestión de tareas diarias usando HTML, CSS y JavaScript, implementando funcionalidades como listas de tareas y recordatorios.', enlace:'http:www.direccion.com'},
  {fecha: '2020', title: 'Curso de Introducción a la Programación', descripcion: 'Completé un curso en línea sobre fundamentos de programación, donde aprendí lenguajes como Python y Java.', enlace:'http:www.direccion.com'}
]);
</script>

<template>
    <ul>
        <li v-for="(item, index) in educacion" :key="index" :style="{ '--fecha-color': fechaColor[index].color}">
        <div class="fecha">{{ item.fecha }}</div>
        <h3 class="title">{{ item.title }}</h3>
        <div class="descripcion">{{ item.descripcion }}</div>
        <!--Aqui vemos con el uso de b-vind (:) que bindeamos el atributo href de html con el item.enlace-->
        <a class="enlace" :href="item.enlace" target="_blank">Saber más</a>
    </li>
    </ul>
</template>

<style scoped>
/* Importar fuente */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");

/* Reseteo de estilos básicos */
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* Estilo para el cuerpo de la página */
body {
  --color: #1a1a2e;
  --bgColor: #f8f9fa;
  --primary: #667eea;
  --secondary: #764ba2;
  --accent: #f093fb;
  min-height: 100vh;
  display: grid;
  align-content: center;
  gap: 2rem;
  padding: 2rem;
  font-family: "Poppins", sans-serif;
  color: var(--color);
  background: linear-gradient(135deg, var(--bgColor) 0%, #e8eaf6 100%);
}

/* Estilos para la lista */
ul {
  margin-top: 2rem;
  --col-gap: 2rem;
  --row-gap: 2.5rem;
  --line-w: 0.3rem;
  display: grid;
  grid-template-columns: var(--line-w) 1fr;
  grid-auto-columns: max-content;
  column-gap: var(--col-gap);
  list-style: none;
  width: min(65rem, 95%);
  margin-inline: auto;
}

/* Línea vertical que conecta los elementos */
ul::before {
  content: "";
  grid-column: 1;
  grid-row: 1 / span 20;
  background: linear-gradient(180deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
  border-radius: calc(var(--line-w) / 2);
  box-shadow: 0 0 20px rgba(102, 126, 234, 0.3);
}

/* Espaciado entre elementos */
ul li:not(:last-child) {
  margin-bottom: var(--row-gap);
}

/* Estilo para cada ítem */
ul li {
  grid-column: 2;
  --inlineP: 1.5rem;
  margin-inline: var(--inlineP);
  grid-row: span 2;
  display: grid;
  grid-template-rows: min-content min-content min-content;
}

/* Estilo para la fecha */
ul li .fecha {
  --dateH: 3.5rem;
  height: var(--dateH);
  margin-inline: calc(var(--inlineP) * -1);
  text-align: center;
  background: linear-gradient(135deg, var(--fecha-color), var(--fecha-color));
  color: white;
  font-size: 1.3rem;
  font-weight: 700;
  display: grid;
  place-content: center;
  position: relative;
  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
  box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
  transition: all 0.3s ease;
}

ul li .fecha:hover {
  transform: translateX(5px);
  box-shadow: 0 6px 20px rgba(102, 126, 234, 0.5);
}

/* Triángulo decorativo */
ul li .fecha::before {
  content: "";
  width: var(--inlineP);
  aspect-ratio: 1;
  background: linear-gradient(135deg, var(--fecha-color), rgba(0, 0, 0, 0.1));
  position: absolute;
  top: 100%;
  clip-path: polygon(0 0, 100% 0, 0 100%);
  right: 0;
  filter: drop-shadow(0 2px 5px rgba(0, 0, 0, 0.1));
}

/* Círculo que conecta */
ul li .fecha::after {
  content: "";
  position: absolute;
  width: 1.2rem;
  aspect-ratio: 1;
  background: var(--bgColor);
  border: 4px solid var(--fecha-color);
  border-radius: 50%;
  top: 50%;
  transform: translate(50%, -50%);
  right: calc(100% + var(--col-gap) + var(--line-w) / 2);
  box-shadow: 0 0 0 4px rgba(102, 126, 234, 0.15);
  transition: all 0.3s ease;
}

ul li .fecha:hover::after {
  transform: translate(50%, -50%) scale(1.15);
  box-shadow: 0 0 0 8px rgba(102, 126, 234, 0.25);
}

/* Estilos para título y descripción */
ul li .title,
ul li .descripcion {
  background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
  position: relative;
  padding-inline: 1.5rem;
  border-radius: 0 16px 16px 0;
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.3);
}

ul li .title {
  overflow: hidden;
  padding-block-start: 1.5rem;
  padding-block-end: 0.8rem;
  font-weight: 700;
  font-size: 1.2rem;
  color: #ffffff;
  border-left: 5px solid var(--fecha-color);
  transition: all 0.3s ease;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.95) 0%, rgba(22, 33, 62, 0.95) 100%);
}

ul li .descripcion {
  padding-block-end: 1.5rem;
  font-weight: 400;
  font-size: 0.95rem;
  color: #e0e0e0;
  line-height: 1.8;
  background: linear-gradient(135deg, rgba(26, 26, 46, 0.9) 0%, rgba(22, 33, 62, 0.9) 100%);
}

/* Sombras suaves */
ul li .title::before,
ul li .descripcion::before {
  content: "";
  position: absolute;
  width: 85%;
  height: 0.4rem;
  background: rgba(102, 126, 234, 0.1);
  left: 50%;
  border-radius: 50%;
  filter: blur(6px);
  transform: translate(-50%, 50%);
}

ul li .title::before {
  bottom: calc(100% + 0.1rem);
}

ul li .descripcion::before {
  z-index: -1;
  bottom: 0.3rem;
}

/* Estilo para el enlace */
ul li .enlace {
  display: inline-block;
  margin-top: 0.8rem;
  padding: 0.6rem 1.2rem;
  background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
  color: white;
  text-decoration: none;
  border-radius: 6px;
  font-weight: 500;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  cursor: pointer;
  box-shadow: 0 4px 10px rgba(102, 126, 234, 0.3);
}

ul li .enlace:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 15px rgba(102, 126, 234, 0.4);
}

ul li .enlace:active {
  transform: translateY(0);
}

/* Efecto hover general en el item */
ul li:hover .title {
  border-left-color: var(--accent);
  color: var(--secondary);
}

/* Media query para pantallas anchas */
@media (min-width: 40rem) {
  ul {
    grid-template-columns: 1fr var(--line-w) 1fr;
  }
  
  ul::before {
    grid-column: 2;
  }
  
  ul li:nth-child(odd) {
    grid-column: 1;
  }
  
  ul li:nth-child(even) {
    grid-column: 3;
  }

  ul li:nth-child(2) {
    grid-row: 2/4;
  }

  /* Ajustes para ítems impares */
  ul li:nth-child(odd) .fecha::before {
    clip-path: polygon(0 0, 100% 0, 100% 100%);
    left: 0;
    right: auto;
  }

  ul li:nth-child(odd) .fecha::after {
    transform: translate(-50%, -50%);
    left: calc(100% + var(--col-gap) + var(--line-w) / 2);
    right: auto;
  }

  ul li:nth-child(odd) .fecha {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
  }

  ul li:nth-child(odd) .title,
  ul li:nth-child(odd) .descripcion {
    border-radius: 16px 0 0 16px;
    border-left: none;
    border-right: 5px solid var(--fecha-color);
  }
}

/* Media query para móviles */
@media (max-width: 768px) {
  body {
    padding: 1rem;
  }

  ul {
    --col-gap: 1.5rem;
    --row-gap: 2rem;
    width: 100%;
  }

  ul li .fecha {
    --dateH: 3rem;
    font-size: 1.1rem;
  }

  ul li .title {
    font-size: 1rem;
    padding-block-start: 1.2rem;
  }

  ul li .descripcion {
    font-size: 0.9rem;
  }
}

/* Créditos */
.credits {
  margin-top: 2rem;
  text-align: center;
  font-size: 0.85rem;
  color: #888;
}

.credits a {
  color: var(--primary);
  text-decoration: none;
  font-weight: 600;
  transition: color 0.3s ease;
}

.credits a:hover {
  color: var(--secondary);
}
</style>