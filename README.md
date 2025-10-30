---
layout: null
---

<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Projetos Kikachan</title>

<style>
/* Reset e scroll suave */
html, body {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
html {
    scroll-behavior: smooth;
}

/* Menu fixo */
nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background: #1b1b1b;
    padding: 10px 0;
    text-align: center;
    z-index: 1000;
}

nav a {
    margin: 0 15px;
    color: white;
    text-decoration: none;
    font-weight: bold;
}

nav a:hover {
    text-decoration: underline;
}

/* Espaço para o menu fixo */
body {
    padding-top: 60px; /* ajusta conforme altura do menu */
}

/* Banner */
header img {
    width: 100%;
    display: block;
}

/* Sessões */
section {
    padding: 30px 20px;
}

/* Projetos */
.projects-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
}

.project-card {
    flex: 1 1 250px;
    max-width: 300px;
    text-align: center;
    position: relative;
    overflow: hidden;
    border-radius: 8px;
}

.project-card img {
    width: 100%;
    height: 300px;
    object-fit: cover;
    border-radius: 8px;
    transition: transform 0.3s ease;
}

.project-card:hover img {
    transform: scale(1.05);
}

.overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 40px;
    background: rgba(0, 0, 0, 0.65);
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: bold;
    font-size: 14px;
    border-radius: 0 0 8px 8px;
    overflow: hidden;
    transform: translateY(100%);
    transition: transform 0.3s ease;
}

.project-card:hover .overlay {
    transform: translateY(0);
}

.project-card p {
    margin-top: 8px;
}

/* Equipe: imagem à esquerda */
.team-member {
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    gap: 20px;
    margin-bottom: 40px;
}

.team-member img {
    width: 180px;
    height: 180px;
    object-fit: cover;
    border-radius: 10px;
}
.team-member .info {
    max-width: 700px;
}
</style>
</head>

<body>

<!-- Menu fixo -->
<nav>
  <a href="#em-andamento">Em andamento</a>
  <a href="#concluidas">Concluídas</a>
  <a href="#equipe">Equipe</a>
</nav>

<!-- Banner -->
<header>
  <img src="https://kikachangames.github.io/projetos/img/banner.png" alt="Banner">
</header>

<!-- Traduções em andamento -->
<section id="em-andamento">
<h1>Traduções em andamento</h1>
<div class="projects-container">
  {% for projeto in site.data.projetos.em_andamento %}
  <div class="project-card">
    <a href="{{ projeto.link }}">
      <img src="{{ projeto.imagem }}">
      <div class="overlay">{{ projeto.progresso }}</div>
    </a>
    <p><b>{{ projeto.nome }}</b><br>Lançamento: {{ projeto.lancamento }}</p>
  </div>
  {% endfor %}
</div>
</section>

<hr>

<!-- Traduções concluídas -->
<section id="concluidas">
<h1>Traduções concluídas</h1>
<div class="projects-container">
  {% for projeto in site.data.projetos.concluidas %}
  <div class="project-card">
    <a href="{{ projeto.link }}">
      <img src="{{ projeto.imagem }}">
      <div class="overlay">{{ projeto.progresso }}</div>
    </a>
    <p><b>{{ projeto.nome }}</b><br>Lançamento: {{ projeto.lancamento }}</p>
  </div>
  {% endfor %}
</div>
</section>

<hr>

<!-- Equipe -->
<section id="equipe">
<h1>Equipe</h1>

<div class="team-member">
  <img src="https://kikachangames.github.io/air/manolo.png" alt="Manolo">
  <div class="info">
    <h3>Manolo-chan</h3>
    <p><b>Líder de projeto, programação e edição de imagens</b></p>
    <p>Tenho uma paixão por Visual Novels e cheguei nesse universo ao aprender Renpy com o objetivo de criar meu próprio jogo! Curto romances, terror e histórias com múltiplos finais, especialmente aquelas ambientadas em escolas! Admiro o trabalho da Key e da 07th Expansion e meu desejo é resgatar o amor pela leitura por meio das VNs.</p>
  </div>
</div>

<div class="team-member">
  <img src="https://kikachangames.github.io/sayooshi/dudas.png" alt="Dudas">
  <div class="info">
    <h3>Dudas</h3>
    <p><b>Tradução e revisão</b></p>
    <p>Eae, galerinha do mal, Beleza? Aqui quem fala é a Dudas. Faz pouco tempo desde que entrei nesse mundo das Visual Novels, e tenho amado desde então. Um dos meus principais objetivos é poder trazer o máximo de LNs para a comunidade brasileira.🙂 Gosto de histórias com drama, terror psicológico, ação e fantasia.</p>
  </div>
</div>

<div class="team-member">
  <img src="https://kikachangames.github.io/sayooshi/alex.png" alt="Alex">
  <div class="info">
    <h3>Alex</h3>
    <p><b>Tradução e revisão</b></p>
    <p>Ex-redator. Atualmente operando como tradutor.</p>
  </div>
</div>

<div class="team-member">
  <img src="https://kikachangames.github.io/higanbana1-pt-br/ceuipsolon.png" alt="Ceuipsolon">
  <div class="info">
    <h3>Ceuipsolon</h3>
    <p><b>Game hacking, revisão e edição de imagens</b></p>
    <p>Olá, meu nome é Ceuipsolon (ou Palpitando no YT). Gosto de explorar o mundo de prosas proporcionadas por VNs que hoje são meu novo mundo de interesse.</p>
  </div>
</div>

</section>

<hr>

<p><small>Última atualização: 25/10/2025.</small></p>
<p><small>Kikachan Games (Desde 2024) <a href="https://kikachangames.github.io/projetos/">Projetos</a> - <a href="https://twitter.com/kikachangames/" target="_blank">X</a> - <a href="https://discord.gg/jsm8yKtu2E" target="_blank">Discord</a> - <a href="https://kikachan-games.itch.io/" target="_blank">Itch</a></small></p>

</body>
</html>
