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
          <button class="btn-primary" @click="scrollToProjects">Ver Proyectos
            Ver Proyectos
          </button>
          <button class="btn-secondary">Contactar</button>
        </div>
      </div>

      <div class="hero-image">
        <div class="image-bg-glow"></div>
        <img src="/tu-foto-sin-fondo.png" alt="Perfil Profesional" />
      </div>
    </section> <section id="mis-proyectos" class="projects-grid">
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
.portfolio-container {
  display: flex;
  flex-direction: column; /* Apila las secciones una debajo de otra */
  align-items: center;
  padding: 0 20px;
}

.hero, .projects-grid {
  width: 100%;
  max-width: 1200px; /* Centra el contenido en pantallas grandes */
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

.hero-image {
  position: relative;
  width: 400px;
}

.hero-image img {
  width: 100%;
  position: relative;
  z-index: 2;
  filter: drop-shadow(0 0 20px rgba(66, 184, 131, 0.3));
}

/* Efecto de brillo detrás de tu foto */
.image-bg-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120%;
  height: 120%;
  background: radial-gradient(circle, rgba(66, 184, 131, 0.2) 0%, transparent 70%);
  z-index: 1;
}

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
.projects-grid {
  max-width: 1200px;
  margin: 4rem auto;
  padding: 0 2rem;
}

.section-title {
  font-size: 2rem;
  color: #42b883;
  margin-bottom: 2rem;
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 3px;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); /* Se adapta al ancho de pantalla */
  gap: 2rem;
  width: 100%;
  margin-top: 3rem;
}

.project-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(66, 184, 131, 0.2);
  border-radius: 15px;
  padding: 1.5rem;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.project-card:hover {
  transform: translateY(-10px);
  border-color: #42b883;
  box-shadow: 0 10px 30px rgba(66, 184, 131, 0.1);
  background: rgba(255, 255, 255, 0.05);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}

.tag {
  background: rgba(66, 184, 131, 0.1);
  color: #42b883;
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: bold;
}

.project-card h3 {
  font-size: 1.4rem;
  margin-bottom: 1rem;
  color: #fff;
}

.project-card p {
  font-size: 0.95rem;
  color: #94a3b8;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.card-footer {
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding-top: 1rem;
  font-size: 0.8rem;
  color: #42b883;
  font-weight: 500;
}
.connect-section {
  padding: 6rem 2rem;
  display: flex;
  justify-content: center;
  background: #0a0a0c;
}

.connect-card {
  text-align: center;
  max-width: 700px;
  padding: 3rem;
  background: rgba(66, 184, 131, 0.05);
  border-radius: 24px;
  border: 1px dashed rgba(66, 184, 131, 0.3);
}

.connect-card p {
  color: #94a3b8;
  font-size: 1.2rem;
  margin-bottom: 2.5rem;
}

.social-links {
  display: flex;
  gap: 1.5rem;
  justify-content: center;
  flex-wrap: wrap;
}

.btn-linkedin, .btn-github {
  text-decoration: none;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-weight: bold;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  gap: 10px;
}

.btn-linkedin {
  background: #0077b5;
  color: white;
}

.btn-linkedin:hover {
  background: #005a87;
  transform: scale(1.05);
}

.btn-github {
  background: #24292e;
  color: white;
  border: 1px solid #444;
}

.btn-github:hover {
  background: #111;
  transform: scale(1.05);
}

.icon {
  font-family: monospace;
  font-size: 1.2rem;
  background: rgba(255,255,255,0.2);
  padding: 2px 6px;
  border-radius: 4px;
}
</style>