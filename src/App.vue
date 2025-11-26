<script setup>
import { ref } from 'vue';

const projetos = ref([
  { id: 1, titulo: 'Residencial Blue Sky', desc: 'Fachada moderna com pele de vidro', img: '/img/FACHADA0.png' },
  { id: 2, titulo: 'Casa Oliveiras', desc: 'Design sustentável com materiais reciclados', img: '/img/FACHADA1.png' },
  { id: 3, titulo: 'Sobrado Horizonte', desc: 'Estrutura inovadora com formas orgânicas', img: '/img/FACHADA2.png' },
  { id: 4, titulo: 'Edifício Inteligente', desc: 'Edifício com automação avançada', img: '/img/FACHADA3.png' },
  { id: 5, titulo: 'Espaço Urbano', desc: 'Espaço urbano com integração verde', img: '/img/FACHADA4.png' }
])
</script>

<template>
  <div class="app-wrapper">

    <header class="navbar">
      <div class="logo">
        <img src="/img/Logo principal.png" alt="Logo" height="50">
      </div>
      <nav>
        <a href="#home">Início</a>
        <a href="#about">Quem Somos</a>
        <a href="#projects">Projetos</a>
        <a href="#location">Localização</a>
        <a href="#contact" class="btn-contato">Contato</a>
      </nav>
    </header>

    <main class="conteudo-moldura">
      
      <section id="home" class="hero">
        <h1>Construindo Sonhos</h1>
        <p>Solidez e confiança em cada metro quadrado.</p>
      </section>
      
      <section id="about">
        <h2>Quem Somos</h2>
        <p>Somos uma empresa dedicada a transformar ideias em realidade, com foco em inovação e sustentabilidade.</p>
      </section>

      <section id="projects">
        <h2>Nossos Projetos</h2>
        <div class="lista-obras">
          <div v-for="item in projetos" :key="item.id" class="projeto-card">
            <img :src="item.img" :alt="item.titulo" />
            <div class="card-info">
              <h3>{{ item.titulo }}</h3>
              <p>{{ item.desc }}</p>
            </div>
          </div>
        </div>
      </section>


      <section id="location">
        <h2>Onde Estamos</h2>
        <div class="grid-mapas">
          <div class="mapa-wrapper">
            <h3>Campos dos Goytacazes</h3>
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3705.596329986166!2d-41.33083565949263!3d-21.75716988016372!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xbdd4492b767af9%3A0xb47aea8caff62a8b!2sRua%20Bar%C3%A3o%20de%20Miracema%2C%20163%20-%20Centro%2C%20Campos%20dos%20Goytacazes%20-%20RJ%2C%2028035-301!5e0!3m2!1spt-BR!2sbr!4v1764192460388!5m2!1spt-BR!2sbr" 
              width="100%" height="300" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
          </div>
          <div class="mapa-wrapper">
            <h3>Itaperuna</h3>
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3719.847203610647!2d-41.90684645950505!3d-21.19822798057499!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xbc61a6371d9911%3A0x672553634da09b4d!2sConstrutora%20Marinho!5e0!3m2!1spt-BR!2sbr!4v1764184339119!5m2!1spt-BR!2sbr" 
              width="100%" height="300" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
          </div>
        </div>
      </section>

      <section id="contact" style="text-align: center;">
        <h2>Fale Conosco</h2>
        <p>Email: contato@construtora.com.br</p>
      </section>

    </main>

    <footer class="footer-moldura">
      <p>© 2025 Empresa de Construção. Todos os direitos reservados.</p>
    </footer>

  </div>
</template>

<style scoped>
/* --- 1. HEADER (NAVBAR) --- */
.navbar {
  /* Fixa no topo */
  position: fixed;
  top: 0;
  left: 0;
  width: 100%; /* Ocupa tudo */
  height: 80px; /* Definir altura ajuda a calcular o padding do body depois */
  
  /* Visual */
  background-color: #fff; /* ou rgba(255,255,255,0.95) para transparência */
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 40px; /* Espaçamento interno lateral */
  z-index: 1000; /* Garante que fique acima de tudo */
  box-sizing: border-box;
}

nav a {
  margin-left: 20px;
  text-decoration: none;
  color: #333;
  font-weight: bold;
  font-size: 0.95rem;
  transition: color 0.3s;
}

nav a:hover {
  color: #076AAE;
}

.btn-contato {
  background-color: #076AAE;
  color: white !important;
  padding: 10px 20px;
  border-radius: 5px;
}


/* --- 2. O CORPO (A MOLDURA) --- */
.conteudo-moldura {
  /* O Pulo do Gato: Margem Top para não ficar escondido atrás do Header Fixo */
  margin-top: 100px; /* 80px do header + 20px de respiro */
  
  /* As Margens Laterais (O efeito de ser mais estreito) */
  margin-left: 50px;
  margin-right: 50px;
  margin-bottom: 50px;
  
  /* Visual da Moldura */
  background-color: #fff;
  border-radius: 15px;
  box-shadow: 0 0 30px rgba(0,0,0,0.5);
  
  /* Garante que o conteúdo interno respeite as bordas arredondadas */
  overflow: hidden; 
  min-height: 80vh;
}


/* --- 3. RODAPÉ (Estilizado para acompanhar a moldura) --- */
.footer-moldura {
  margin: 0 50px 50px 50px; /* Mesmas margens do main */
  background-color: #f1f1f1;
  text-align: center;
  padding: 20px;
  border-radius: 10px;
  color: #666;
}


/* --- DEMAIS ESTILOS (Hero, Maps, etc) --- */
.hero {
  background-color: #f8f9fa;
  padding: 120px 20px;
  text-align: center;
}

section {
  padding: 60px 40px;
}

.grid-mapas {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
}

.mapa-wrapper iframe {
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

.lista-obras {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
}

.projeto-card {
  border: 1px solid #eee;
  border-radius: 8px;
  overflow: hidden;
}

.projeto-card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card-info {
  padding: 15px;
}

/* Responsividade Básica */
@media (max-width: 768px) {
  .conteudo-moldura, .footer-moldura {
    margin-left: 10px;
    margin-right: 10px;
  }
  
  .navbar {
    flex-direction: column;
    height: auto;
    padding: 15px;
  }
  
  .conteudo-moldura {
    margin-top: 160px; /* Aumenta margem topo pois header cresceu */
  }

  .grid-mapas {
    grid-template-columns: 1fr;
  }
}
</style>