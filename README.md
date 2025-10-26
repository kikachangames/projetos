<!-- Reset de margens/padding e scroll suave -->
<style>
html, body {
    margin: 0;
    padding: 0;
    padding-top: 25px; /* Espaço para o menu */
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

section {
    padding-top: 20px; /* altura do menu fixo */
}

/* menu */
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
}

nav a:hover {
    text-decoration: underline;
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
    transform: translateY(100%); /* começa fora da imagem */
    transition: transform 0.3s ease;
}

.project-card:hover .overlay {
    transform: translateY(0); /* sobe ao passar o mouse */
}

.project-card p {
    margin-top: 8px;
}
</style>

<!-- Menu fixo -->
<nav>
  <a href="#em-andamento">Em andamento</a>
  <a href="#concluidas">Concluídas</a>
  <a href="#equipe">Equipe</a>
</nav>

<section id="em-andamento">
    
<h1>Traduções em andamento</h1>
<div class="projects-container">
  {% assign projetos_ordenados = site.data.projetos.em_andamento | sort: "status" | reverse %}
  {% for projeto in projetos_ordenados %}
  <div class="project-card">
    <a href="{{ projeto.link }}">
      <img src="{{ projeto.imagem }}">
      <div class="overlay"><b>Progresso: {{ projeto.status | replace: '.', ',' }}% traduzido</b></div>
    </a>
    <p><b>{{ projeto.nome }}</b><br>Lançamento: {{ projeto.lancamento }}</p>
  </div>
  {% endfor %}
</div>
    
</section>
<hr>

<section id="concluidas">
  
<h1>Traduções concluídas</h1>
<div class="projects-container">
  {% for projeto in site.data.projetos.concluidas %}
  <div class="project-card">
    <a href="{{ projeto.link }}">
      <img src="{{ projeto.imagem }}">
      <div class="overlay">Progresso: {{ projeto.status }}</div>
    </a>
    <p><b>{{ projeto.nome }}</b><br>Lançamento: {{ projeto.lancamento }}</p>
  </div>
  {% endfor %}
</div>

</section>

<hr>

<section id="equipe">
<h1>Equipe</h1>

<div style="display: flex; flex-direction: column; gap: 40px;">

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/air/manolo.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>Manolo-chan</h3>
      <p><b>Líder de projetos, tradução e edição de imagens</b></p>
      <p>Tenho uma paixão por Visual Novels e cheguei nesse universo ao aprender Renpy com o objetivo de criar meu próprio jogo! Curto romances, terror e histórias com múltiplos finais, especialmente aquelas ambientadas em escolas! Admiro o trabalho da Key e da 07th Expansion e meu desejo é resgatar o amor pela leitura por meio das VNs.</p>
    </div>
  </div>

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/air/hin.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>Hinrong</h3>
      <p><b>Game hacking e revisão</b></p>
      <p>Gosto de Suzumiya Haruhi, Scott Pilgrim, Rewrite, Little Busters! e Danganronpa. Faço de tudo e mais um pouco nos projetos e sou apaixonado por fã-traduções. Prazer te conhecer!</p>
    </div>
  </div>

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/sayooshi/dudas.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>Dudas</h3>
      <p><b>Tradução e revisão</b></p>
      <p>Eae, galerinha do mal, Beleza? Aqui quem fala é a Dudas. Faz pouco tempo desde que entrei nesse mundo das Visual Novels, e tenho amado desde então. Um dos meus principais objetivos é poder trazer o máximo de LNs para a comunidade brasileira.🙂 Gosto de histórias com drama, terror psicológico, ação e fantasia.</p>
    </div>
  </div>

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/higanbana1-pt-br/mateus.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>0Mateus</h3>
      <p><b>Game Hacking, revisão e Quality Check</b></p>
      <p>Olá pessoal! Gosto muito de Higurashi, Umineko e outras visual novels. Curto muito o trabalho da 07th Expansion e passo o tempo assistindo animes e jogando.</p>
    </div>
  </div>

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/projetos/img/takumi.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>Takumi</h3>
      <p><b>Tradução</b></p>
      <p>Olá, sou o Takumi, tenho o canal "Takumi Enferrujado" no Youtube onde falo de jogos, animes e visual novels do meu interesse. Sou um leitor e tradutor de longa data no ramo que quer atrair o máximo de gente para o ramo também.</p>
    </div>
  </div>

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/higanbana1-pt-br/ceuipsolon.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>Ceuipsolon</h3>
      <p><b>Game Hacking, revisão, edição de imagens</b></p>
      <p>Olá, meu nome é Ceuipsolon (ou Palpitando no YT). Gosto de explorar o mundo de prosas proporcionadas por VNs que hoje são meu novo mundo de interesse.</p>
    </div>
  </div>

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/moon/kazuki.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>Kazuki Minoru</h3>
      <p><b>Revisão e Quality Check</b></p>
      <p>Olá pessoal! Bom, desde que comecei a jogar visual novels e outros jogos com traduções de fãs, sempre admirei quem faz elas, então pensei que podia fazer parte disso de alguma forma, e aqui estou!</p>
    </div>
  </div>

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/sayooshi/alex.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>Alex</h3>
      <p><b>Tradução e revisão</b></p>
      <p>Ex-redator. Atualmente operando como tradutor.</p>
    </div>
  </div>

  <div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
    <img src="https://kikachangames.github.io/air/div.png" style="width: 180px; height: 180px; object-fit: cover; border-radius: 10px;">
    <div style="max-width: 700px;">
      <h3>Div-lu</h3>
      <p><b>Tradução, revisão e edição de imagens</b></p>
      <p>Olá! Sou o Div-lu, mas podem chamar-me só de Div. Amo RPGs, novels e cultura japonesa em geral, especialmente obras como Chaos Head, Air, Clannad, Rewrite e Ace Attorney. Sou fã de traduções feitas por fãs, pois transmitem um carinho especial pela obra.</p>
    </div>
  </div>

</div>
</section>

<hr>


<p><small>Última atualização: 25/10/2025.</small></p>
<p><small>Kikachan Games (Desde 2024) <a href="https://kikachangames.github.io/projetos/">Projetos</a> - <a href="https://twitter.com/kikachangames/" target="_blank">X</a> - <a href="https://discord.gg/jsm8yKtu2E" target="_blank">Discord</a> - <a href="https://kikachan-games.itch.io/" target="_blank">Itch</a></small></p>
