<script setup lang="ts">
import { misProyectos } from './data/proyectos';

const scrollToProjects = () => {
  const el = document.getElementById('mis-proyectos');
  if (el) el.scrollIntoView({ behavior: 'smooth' });
};
</script>

<template>
  <main class="portfolio-container">
    <section class="hero">
      <div class="hero-content">
        <h1 class="glow-text">Desarrollador Full-Stack</h1>
        <p class="subtitle">Software Personalizado & Sistemas TI</p>
        
        <div class="bio">
          <p>
            Desarrollador junior, experiencia en el contacto con clientes.
            <strong>Vue 3, TypeScript, HTML, Css, JavaScript, PHP y Docker</strong>.
          </p>
        </div>
        
        <div class="cta-buttons">
          <button class="btn-primary" @click="scrollToProjects">Ver Proyectos </button>
          <button class="btn-secondary">Contactar</button>
        </div>
      </div>
    </section>

    <section id="sobre-mi" class="about-section">
      <div class="container about-grid">
        <div class="about-image">
          <img src="/tu-foto-sin-fondo.png" alt="Gines Christian" class="profile-img">
          <div class="glow-effect"></div>
        </div>

        <div class="about-content">
          <h2>Sobre Mí</h2>
          <p>
            ¡Hola! Soy <strong>Gines Christian</strong>, un desarrollador apasionado por crear soluciones tecnológicas que resuelven problemas reales. 
          </p>
          <p>
            Mi enfoque combina la curiosidad técnica con la experiencia práctica. He desarrollado desde <strong>sistemas de gestión integral para empresas (ERP)</strong>, controlando stock y finanzas, hasta modernas <strong>aplicaciones web e-commerce</strong>.
          </p>
          <p>
            Me especializo en el ecosistema de JavaScript (Vue 3, Vite) y tengo experiencia sólida gestionando bases de datos y despliegues con Docker. Mi objetivo es seguir creciendo en entornos desafiantes donde pueda aportar valor a través del código limpio y eficiente.
          </p>
          
          <div class="skills-mini">
            <span>#ResoluciónDeProblemas</span>
            <span>#DesarrolloFullStack</span>
            <span>#SistemasTI</span>
          </div>
        </div>
      </div>
    </section>

    <section id="mis-proyectos" class="projects-grid">
      <h2 class="section-title">Soluciones de Software Personalizado</h2>
      
      <div class="grid-container">
        <div v-for="proyecto in misProyectos" :key="proyecto.id" class="project-card">
          <div class="card-header">
            <span class="tag">{{ proyecto.categoria }}</span>
          </div>
          
          <h3>{{ proyecto.titulo }}</h3>
          <p>{{ proyecto.descripcion }}</p>
          
          <div class="card-footer">
            <span class="tech-stack">
              {{ proyecto.tecnologias.join(' • ') }}
            </span>
            <br>
            <a :href="proyecto.linkGithub" target="_blank" class="project-link">Ver Código →</a>
          </div>
        </div>
      </div>
    </section>

    <section class="connect-section">
      <div class="connect-card">
        <h2 class="section-title">¿Te interesa mi perfil?</h2>
        <p>Estoy abierto a nuevas oportunidades y colaboraciones en proyectos de Software TI.</p>
        
        <div class="social-links">
          <a href="https://www.linkedin.com/in/gines-christian-lopez-romera-6862182a6/" target="_blank" class="btn-linkedin">
            <span class="icon">in</span> Ver Perfil de LinkedIn
          </a>
          
          <a href="https://github.com/gineschristian" target="_blank" class="btn-github">
            <span class="icon">git</span> Revisar mi Código
          </a>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
/* MANTENEMOS TU DISEÑO ORIGINAL */
.portfolio-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 0 20px;
}

.hero, .projects-grid, .about-section {
  width: 100%;
  max-width: 1200px;
  margin-bottom: 5rem;
}

.glow-text {
  font-size: 4rem;
  font-weight: 800;
  background: linear-gradient(to right, #42b883, #35495e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 0.5rem;
}

.subtitle {
  font-size: 1.5rem;
  color: #94a3b8;
  margin-bottom: 2rem;
  letter-spacing: 2px;
}

/* --- CORRECCIÓN DE LA FOTO --- */
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
  gap: 3rem;
  align-items: center;
}

.about-image {
  position: relative;
  display: flex;
  justify-content: center;
}

.profile-img {
  width: 100%;
  max-width: 250px; /* AQUÍ REDUCIMOS EL TAMAÑO */
  height: auto;
  border-radius: 20px;
  position: relative;
  z-index: 2;
  filter: drop-shadow(0 0 15px rgba(66, 184, 131, 0.3));
}

.glow-effect {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 130%;
  height: 130%;
  background: radial-gradient(circle, rgba(66, 184, 131, 0.15) 0%, transparent 70%);
  z-index: 1;
}

/* --- RESTO DE TU DISEÑO --- */
.btn-primary {
  background: #42b883;
  color: #0f172a;
  padding: 0.8rem 2rem;
  border-radius: 8px;
  font-weight: 700;
  border: none;
  cursor: pointer;
  margin-right: 1rem;
}

.btn-secondary {
  background: transparent;
  color: #42b883;
  padding: 0.8rem 2rem;
  border-radius: 8px;
  font-weight: 700;
  border: 2px solid #42b883;
  cursor: pointer;
}

.about-content h2, .section-title {
  font-size: 2rem;
  color: #42b883;
  margin-bottom: 1.5rem;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.about-content p {
  color: #cbd5e1;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.skills-mini {
  display: flex;
  gap: 10px;
  color: #42b883;
  font-family: monospace;
  font-weight: bold;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2rem;
}

.project-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(66, 184, 131, 0.2);
  border-radius: 15px;
  padding: 1.5rem;
  transition: all 0.3s ease;
}

.tag {
  background: rgba(66, 184, 131, 0.1);
  color: #42b883;
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 0.75rem;
}

.connect-card {
  text-align: center;
  padding: 3rem;
  background: rgba(66, 184, 131, 0.05);
  border-radius: 24px;
  border: 1px dashed rgba(66, 184, 131, 0.3);
}

.social-links {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
}

@media (max-width: 768px) {
  .about-grid {
    grid-template-columns: 1fr;
    text-align: center;
  }
  .profile-img {
    max-width: 200px;
  }
}
</style>