<script setup>
const title = "Juan Moreno";
const descripcion = "Técnico Universitario en Programación - UTN";
const residencia = "San Rafael, Mendoza, Argentina";
const presentacion = "Hola, Bienvenido a mi portafolio de proyectos. Soy un estudiante en programacion de la UTN San Rafael";
const redesociales = [
  { id: 1, name: "linkedin", src: "/src/assets/linkedin_icon.svg", url: "https://www.linkedin.com/in/juan-e-moreno-1006a3391/" },
  { id: 2, name: "instagram", src: "/src/assets/instagram_icon.svg", url: "https://www.instagram.com/moreno_juan18?igsh=MTRlNGdxMzNhbXoybg==" },
  { id: 3, name: "github", src: "/src/assets/github_icon.svg", url: "https://github.com/JuanMoreno18" },
];
const telefono = "+54 9 2604-056016";
</script>

<template>
  <section class="datos-personales">
    <div class="card">
      <!-- Sección de encabezado -->
      <div class="header-section">
        <h1 class="nombre">{{ title }}</h1>
        <h2 class="titulo">{{ descripcion }}</h2>
      </div>

      <!-- Sección de presentación -->
      <div class="presentacion-section">
        <p class="descripcion">{{ presentacion }}</p>
      </div>

      <!-- Redes sociales -->
      <div class="redes-section">
        <h3 class="section-title">Conecta conmigo</h3>
        <ul class="container-lista">
  <li v-for="red in redesociales" :key="red.id">
    <a 
      :href="red.url" 
      class="social-link" 
      :aria-label="red.name"
      target="_blank" 
      rel="noopener noreferrer"
    >
      <img class="icon-redsocial" :src="red.src" :alt="red.name" />
    </a>
  </li>
</ul>
      </div>

      <!-- Información de contacto -->
      <div class="contacto-section">
        <div class="contacto-item">
          <span class="icon">📱</span>
          <span class="contacto-texto">{{ telefono }}</span>
        </div>
        <div class="contacto-item">
          <span class="icon">📍</span>
          <span class="contacto-texto">{{ residencia }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.datos-personales {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 20px;
  background: linear-gradient(135deg, #2d608f 0%, #9c450c 100%);
}

.card {
  background: linear-gradient(145deg, #1e2a35 0%, #2c3e50 100%);
  border-radius: 20px;
  padding: 50px 40px;
  max-width: 700px;
  width: 100%;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.4);
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: transform 0.3s ease;
}

.header-section {
  margin-bottom: 30px;
  padding-bottom: 25px;
  border-bottom: 2px solid rgba(255, 255, 255, 0.1);
}

.nombre {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 10px;
  background: linear-gradient(135deg, #ffffff 0%, #f16406 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  cursor: pointer;
  position: relative;
  display: inline-block;
  transition: all 0.3s ease;
}

.nombre::before {
  content: attr(data-text);
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #ffffff 0%, #f16406 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  filter: blur(10px);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.nombre:hover::before {
  opacity: 0.8;
}

.nombre:hover {
  filter: drop-shadow(0 0 20px rgba(241, 100, 6, 0.6))
         drop-shadow(0 0 40px rgba(241, 100, 6, 0.4))
         drop-shadow(0 0 60px rgba(241, 100, 6, 0.2));
  transform: scale(1.02);
}

.titulo {
  font-size: 1.3rem;
  color: #ffffff;
  font-weight: 400;
  letter-spacing: 0.5px;
}

.presentacion-section {
  margin-bottom: 35px;
}

.descripcion {
  font-size: 1.15rem;
  line-height: 1.7;
  color: #ffffff;
  font-weight: 400;
  text-align: center;
}

.redes-section {
  margin-bottom: 35px;
  padding: 30px 0;
  background: rgba(255, 255, 255, 0.03);
  border-radius: 15px;
}

.section-title {
  font-size: 1.3rem;
  font-weight: 600;
  margin-bottom: 20px;
  color: #cbd5e0;
  text-align: center;
}

.container-lista {
  display: flex;
  justify-content: center;
  gap: 15px;
  list-style: none;
  padding: 0;
  margin: 0;
  flex-wrap: wrap;
}

.social-link {
  display: block;
  transition: transform 0.3s ease;
}

.social-link:hover {
  transform: translateY(-5px);
}

.icon-redsocial {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #f0f4f8 0%, #d9e2ec 100%);
  border-radius: 50%;
  padding: 10px;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
}

.icon-redsocial:hover {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  box-shadow: 0 6px 25px rgba(102, 126, 234, 0.5);
  transform: scale(1.1);
}

.contacto-section {
  display: flex;
  flex-direction: column;
  gap: 15px;
  margin-top: 30px;
  padding-top: 25px;
  border-top: 2px solid rgba(255, 255, 255, 0.1);
}

.contacto-item {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  padding: 12px 20px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  transition: background 0.3s ease;
}

.icon {
  font-size: 1.5rem;
}

.contacto-texto {
  font-size: 1.1rem;
  color: #e2e8f0;
  font-weight: 500;
}

@media (max-width: 768px) {
  .card {
    padding: 35px 25px;
  }

  .nombre {
    font-size: 2.2rem;
  }

  .titulo {
    font-size: 1.1rem;
  }

  .descripcion {
    font-size: 1rem;
  }

  .icon-redsocial {
    width: 45px;
    height: 45px;
  }

  .contacto-texto {
    font-size: 0.95rem;
  }
}
</style>