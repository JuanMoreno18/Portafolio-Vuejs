<script setup>
import Proyecto1 from '/src/assets/proyecto1.png'
import Proyecto2 from '/src/assets/proyecto2.png'
import Proyecto3 from '/src/assets/proyecto3.png'
import Proyecto4 from '/src/assets/proyecto4.png'

import { ref } from 'vue';
var misProyectos = ref([]);
misProyectos.value = ([

{
    id: 1,
    src: Proyecto1,
    titulo: "Portafolio Web (2025)",
    descripcion: "Diseñé y desarrollé mi portafolio web desde cero con HTML, CSS y JavaScript, mostrando mis proyectos y formación.",
    projectoLink: "https://portafolioweb-juanm.netlify.app/",
    githublink: "https://github.com/usuario/curso-online"
},
{
    id: 2,
    src: Proyecto2,
    titulo: "Proyecto Académico - Sistema de Restaurante (2025)",
    descripcion: "Diseñamos un programa en Pseint y rediseñado en Java sobre un sistema de pedidos en un restaurante.",
    projectoLink: "https://www.youtube.com/watch?v=mVpUDBsDrZI",
    githublink: "https://github.com/usuario/inventario-app"
},
{
    id: 3,
    src: Proyecto3,
    titulo: "Portafolio grupal en vuej(2025)",
    descripcion: "Creamos un portafolio grupal en vuej para la tecnicatura de programacion de nuestro equipo Escuadron Lobo.",
    projectoLink: "https://portafolio-escuadronlobo.netlify.app/#Top",
    githublink: "https://github.com/usuario/agencia-landing"
},
{
    id: 4,
    src: Proyecto4,
    titulo: "Proyecto final Ingles I (2025)",
    descripcion: "Desarrollé junto a mi equipo de trabajo un video explicativo en inglés como parte de la cátedra de Inglés Técnico, presentando una aplicación de sistema de pedidos",
    projectoLink: "https://drive.google.com/file/d/1cPmCz_bfWDtisGxR1lRpusifvb4j_9Vv/view",
}


])

</script>

<template>
<!-- Aquí va el código HTML de la galería de proyectos -->
    <div class="galeria">
        <!-- Itera sobre cada proyecto en la lista de misProyectos -->
        <!-- key es una propiedad especial que se utiliza para identificar de forma única cada elemento en una lista de Vue.js -->
        <div class="proyecto" v-for="proyecto in misProyectos" :key="proyecto.id">
            <!-- Muestra la imagen del proyecto utilizando : que es una directiva de enlace de atributo en Vue.js -->
            <img :src="proyecto.src" :alt="proyecto.titulo">
            <div class="proyecto-info">
                <!-- Muestra el título y la descripción del proyecto utilizando la interpolación de Vue.js -->
                <h3>{{ proyecto.titulo }}</h3>
                <p>{{ proyecto.descripcion }}</p>
                <div class="proyecto-links">
                    <a :href="proyecto.projectoLink" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Proyecto</a>
                    <a :href="proyecto.githubLink" class="github-link" target="_blank" rel="noopener noreferrer">Ver Codigo en GitHub</a>
                </div>
            </div>
        </div>
    </div>
    
     <!-- <div class="galeria">
        <div class="proyecto-card">
            <img src="/src/assets/annidada-tech.jpg" alt="Proyecto 1">
            <div class="proyecto-info">
                <h3>Ecommerce</h3>
                <p>Cree una plataforma de comercio electronico que incrementa las ventas en un 35% durante el primer año</p>
                <div class="proyecto-links">
                    <a href="https://proyecto1.com" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Proyecto</a>
                    <a href="https://github.com/usuario/proyecto1" class="github-link" target="_blank"
                        rel="noopener noreferrer">Ver Codigo en GitHub</a>
                </div>
            </div>
        </div>
        <div class="proyecto-card">
            <img src="/src/assets/annidada-tech.jpg" alt="Proyecto 1">
            <div class="proyecto-info">
                <h3>Ecommerce</h3>
                <p>Cree una plataforma de comercio electronico que incrementa las ventas en un 35% durante el primer año</p>
                <div class="proyecto-links">
                    <a href="https://proyecto1.com" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Proyecto</a>
                    <a href="https://github.com/usuario/proyecto1" class="github-link" target="_blank"
                        rel="noopener noreferrer">Ver Codigo en GitHub</a>
                </div>
            </div>
        </div>
        <div class="proyecto-card">
            <img src="/src/assets/annidada-tech.jpg" alt="Proyecto 1">
            <div class="proyecto-info">
                <h3>Ecommerce</h3>
                <p>Cree una plataforma de comercio electronico que incrementa las ventas en un 35% durante el primer año</p>
                <div class="proyecto-links">
                    <a href="https://proyecto1.com" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver Proyecto</a>
                    <a href="https://github.com/usuario/proyecto1" class="github-link" target="_blank"
                        rel="noopener noreferrer">Ver Codigo en GitHub</a>
                </div>
            </div>
        </div>
    </div>  -->
</template>

<style scoped>
.galeria {
    /* Establece el ancho de la galería al 100% del contenedor padre */
    width: 100%;
    /* Establece la altura de la galería al 100% del contenedor padre */
    height: 100%;
    /* Utiliza flexbox para organizar los elementos hijos en la galería */
    display: flex;
    /* Permite que los elementos se ajusten y pasen a la siguiente línea si no caben en una sola fila */
    flex-wrap: wrap;
    /* Establece un espacio de 20px entre los elementos de la galería */
    gap: 20px;
    /* Agrega un padding de 20px alrededor de la galería */
    padding: 20px;
    /* Centra los elementos hijos horizontalmente */
    justify-content: center;
    /* Aplica un fondo con un degradado de colores */
    background: linear-gradient(-45deg, #e21526, #03346E, #6EACDA, #E2E2B6);
    /* Ajusta el tamaño del fondo para que cubra el área completa */
    background-size: 400% 400%;
    /* Aplica una animación al fondo que dura 15 segundos, tiene una transición suave y se repite infinitamente */
    animation: gradient 15s ease infinite;
}

/* Define una animación llamada 'gradient' para cambiar la posición del fondo */
@keyframes gradient {
   
    /* Al inicio, el fondo está posicionado en el 0% horizontal y 50% vertical */
    0% {
        background-position: 0% 50%;
    }
    
    /* A la mitad de la animación, el fondo se desplaza al 100% horizontal y 50% vertical */
    50% {
        background-position: 100% 50%;
    }
    
    /* Al final, el fondo vuelve a la posición inicial */
    100% {
        background-position: 0% 50%;
    }
}
/* La clase 'proyecto' es el contenedor individual de cada proyecto */
.proyecto {
    /* Utiliza flexbox para organizar el contenido del proyecto en una columna */
    display: flex;
    /* Establece la dirección de los elementos en columna */
    flex-direction: column;
    /* Aplica un borde de 2px sólido y color gris claro (#ddd) alrededor del proyecto */
    border: 2px solid #ddd;
    /* Redondea las esquinas del contenedor */
    border-radius: 8px;
    /* Oculta cualquier contenido que se desborde del contenedor */
    overflow: hidden;
    /* Establece un color de fondo claro para el proyecto */
    background-color: #f9f9f9;
    /* Define el ancho máximo del proyecto en 222px */
    max-width: 222px;
    /* Hace que el contenedor se ajuste flexiblemente ocupando al menos 300px de ancho */
    flex: 1 1 300px;
    min-height: 100%;
}

/* Estilo para las imágenes dentro del contenedor 'proyecto' */
.proyecto img {
  width: 200%;
  height: 180px;
  object-fit: cover;
  display: block;
}

/* La clase 'proyecto-info' contiene la información del proyecto */
.proyecto-info {
    /* Agrega un padding de 15px alrededor de la información */
    padding: 15px;
    /* Centra el texto dentro del contenedor */
    text-align: center;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
}

/* Estilo para los títulos de los proyectos */
.proyecto-info h3 {
    /* Establece un margen superior e inferior de 10px */
    margin: 10px 0;
    /* Define el tamaño de la fuente a 1.3em (relativo al tamaño de fuente del contenedor) */
    font-size: 1.3em;
    /* Aplica un color gris oscuro (#333) al texto */
    color: #333;
}
/* Estilo para los párrafos de los proyectos */
.proyecto-info p {
    flex-grow: 1;
    /* Establece un margen superior e inferior de 10px */
    margin: 10px 0;
    /* Define el tamaño de la fuente a 1em (igual al tamaño de fuente base) */
    font-size: 1em;
    /* Aplica un color gris (#666) al texto */
    color: #666;
}

/* La clase 'proyecto-links' organiza los enlaces y botones del proyecto */
.proyecto-links {
    /* Utiliza flexbox para organizar los enlaces en una columna */
    display: flex;
    /* Establece la dirección de los elementos en columna */
    flex-direction: column;
    /* Establece un espacio de 10px entre los elementos */
    gap: 10px;
    /* Agrega un margen superior de 10px */
    margin-top: auto;
}

/* Estilo para el botón 'Ver Más' dentro de la clase 'proyecto-links' */
.proyecto-links .btn-ver-mas {
    /* Aplica un color de fondo azul (#007BFF) */

    background-color: #007BFF;
    /* Aplica un color de texto blanco */
    color: #fff;
    /* Agrega un padding de 10px en vertical y 15px en horizontal */
    padding: 10px 15px;
    /* Redondea las esquinas del botón */
    border-radius: 5px;
    /* Elimina el subrayado del texto */
    text-decoration: none;
    /* Aplica una transición suave al cambiar el color de fondo */
    transition: background-color 0.3s;
}

/* Estilo para cuando el botón 'Ver Más' es hover */
.proyecto-links .btn-ver-mas:hover {
    /* Cambia el color de fondo a un azul más oscuro (#0056b3) */
    background-color: #0056b3;
}

/* Estilo para el enlace a GitHub dentro de la clase 'proyecto-links' */


/* Estilo para cuando el enlace a GitHub es hover */
.proyecto-links .github-link:hover {
    /* Añade un subrayado al texto */
    text-decoration: underline;
}
@media (min-width: 768px) {
    .galeria {
        align-items: stretch;
    }
}
@media (min-width: 375px) and (max-width: 425px) {
  .galeria {
    grid-template-columns: repeat(2, 1fr);
    gap: 8px;
    padding: 2px;
  }

  .proyecto {
    max-width: 95%;
    border-radius: 8px;
  }

  .proyecto img {
    height: 120px;
  }

  .proyecto-info {
    padding: 1px;
  }

  .proyecto-info h3 {
    font-size: 1em;
    margin: 0px 0;
  }

  .proyecto-info p {
    font-size: 0.85em;
    margin: 0px 0;
    line-height: 1.3;
  }

  .proyecto-links {
    gap: 0px;
    margin-top: 2px;
  }

  .btn-ver-mas {
    padding: 6px 10px;
    font-size: 0.85em;
  }

  .github-link {
    font-size: 0.8em;
    padding: 6px;
  }
}

</style>