<template>
  <nav class="navbar">
    <div class="navbar-menu">
      <ul>
        <li v-for="nav in navegacion" :key="nav.id">
          <a :href="nav.enlace">{{ nav.nombre }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

const navegacion = ref([
  { id: 1, nombre: 'Educacion', enlace: '#educacion' },
  { id: 2, nombre: 'Experiencia', enlace: '#experiencia' },
  { id: 3, nombre: 'Proyectos', enlace: '#proyectos' },
  { id: 4, nombre: 'Habilidades', enlace: '#habilidades' },
  { id: 5, nombre: 'Intereses', enlace: '#intereses' },
]);
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  max-width: 1135px;
  width: 90%;
  background-color: rgb(236, 75, 11);
  color: #fff;
  padding: 0.5rem 1rem;
  z-index: 100;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
  border-radius: 0 0 10px 10px;
}

.navbar-menu {
  display: flex;
  justify-content: center;
}

ul {
  list-style: none;
  display: flex;
  gap: 12px;
  margin: 0;
  padding: 0;
  flex-wrap: wrap; /* ✅ permite que bajen si no entran */
}

a {
  border: 1px solid hsla(160, 100%, 37%, 0.2);
  border-radius: 5px;
  text-decoration: none;
  transition: 0.3s;
  padding: 6px 10px;
  color: #fff;
}

a:hover {
  background-color: hsla(160, 100%, 37%, 0.2);
}

/* 🔸 Responsive general hasta 768px */
@media (max-width: 768px) {
  .navbar {
    width: 95%;
  }

  .navbar-menu {
    justify-content: center;
  }
}

/* 🔸 Rango específico entre 375px y 425px */
@media (max-width: 425px) and (min-width: 375px) {
  .navbar {
    width: 100%;
    padding: 0.4rem;
  }

  ul {
    gap: 8px;
    justify-content: center;
  }

  a {
    font-size: 0.85rem;
    padding: 5px 7px;
  }
}
</style>
