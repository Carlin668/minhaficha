<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Ficha RPG Sete</title>
  <style>
    body {
      font-family: "Georgia", serif;
      background-color: #f3e5c0;
      background-image: url("papel.jpg");
      background-size: cover;
      padding: 20px;
      color: #222;
      transition: background-color 0.8s;
    }

    h1 {
      text-align: center;
      font-size: 36px;
      margin-bottom: 20px;
    }

    .personagens {
      display: flex;
      justify-content: center;
      gap: 30px;
      margin-bottom: 20px;
    }

    .personagem {
      cursor: pointer;
      border: 3px solid #333;
      border-radius: 8px;
      overflow: hidden;
      width: 120px;
      transition: transform 0.3s;
    }

    .personagem img {
      width: 100%;
      animation: respirar 3s infinite alternate ease-in-out;
    }

    .personagem:hover {
      transform: scale(1.05);
    }

    @keyframes respirar {
      0% { transform: scale(1); }
      100% { transform: scale(1.02); }
    }

    .ficha {
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
      background: rgba(255, 255, 255, 0.95);
      border-radius: 10px;
      box-shadow: 0 0 10px #0004;
    }

    .ficha input, .ficha textarea {
      width: 100%;
      margin-bottom: 10px;
      padding: 5px;
      font-size: 14px;
      border: 1px solid #aaa;
      border-radius: 4px;
    }

    .coluna {
      display: inline-block;
      vertical-align: top;
      width: 48%;
    }

    .prof {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 8px;
    }

    .prof input {
      width: 40px;
      margin-left: 5px;
    }

    .prof button {
      padding: 3px 8px;
      margin-left: 5px;
    }

    .tema-roxo {
      background-color: #2d0c40;
      color: #eee;
    }

    .tema-branco {
      background-color: #f0f0f0;
      color: #333;
    }

    .tema-preto {
      background-color: #111;
      color: #eee;
    }
  <div class="personagem" onclick="selecionarPersonagem('cavaleiro')">
  <img src="cavaleiro.png" alt="Cavaleiro">
</div>

    .mochila, .anotacoes, .habilidades {
      margin-top: 10px;
    }

    .resumos input {
      width: 70px;
      display: inline-block;
      margin-right: 10px;
    }

    .btns-salvar {
      text-align: center;
      margin-top: 15px;
    }

    .btns-salvar button {
      padding: 8px 15px;
      margin: 5px;
    }
  </style>
</head>
<body>

<h1>Ficha do Personagem</h1>

<div class="personagens">
  <div class="personagem" onclick="selecionarPersonagem('roxo')">
    <img src="roxo.png" alt="Renegado Roxo">
  </div>
  <div class="personagem" onclick="selecionarPersonagem('branco')">
    <img src="branco.png" alt="Loba Branca">
  </div>
  <div class="personagem" onclick="selecionarPersonagem('preto')">
    <img src="preto.png" alt="Rei Esqueleto">
  </div><div class="personagem" onclick="selecionarPersonagem('cavaleiro')">
  <img src="cavaleiro.png" alt="Cavaleiro">
</div>
</div>

<audio id="audio"></audio>

<div class="ficha" id="fichaBox">
  <input id="nome" placeholder="Nome do personagem">
  <input id="classe" placeholder="Classe">
  <input id="elemento" placeholder="Elemento (ex: Sangue, Flora)">
  <textarea id="anotacoes" placeholder="Anotações gerais"></textarea>

  <div class="resumos">
    <input id="vida" placeholder="Vida">
    <input id="armadura" placeholder="Armadura">
    <input id="energia" placeholder="Energia">
    <input id="defesa" placeholder="Defesa">
  </div>

  <div class="coluna" id="coluna1">
    <h3>Força</h3>
    <div class="prof">Combate <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Pontaria <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Arremessar <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Contra-Ataque <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Constituição <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>

    <h3>Agilidade</h3>
    <div class="prof">Esquiva <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Furtividade <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Acrobacia <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>

    <h3>Expansão</h3>
    <div class="prof">Poder <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Arcadismo <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Ocultismo <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Ritual <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
  </div>

  <div class="coluna" id="coluna2">
    <h3>Intelecto</h3>
    <div class="prof">História <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Tradição <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Explorar <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Escutar <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Estudo <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Sobrevivência <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Medicina <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Resistência Mental <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Controle do Sete <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>

    <h3>Sociais</h3>
    <div class="prof">Carisma <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Intimidar <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
    <div class="prof">Persuadir <input type="number" value="0"><button onclick="rolarComPonto(this)">🎲</button></div>
  </div>

  <div class="habilidades">
    <textarea id="habilidades" placeholder="Habilidades do personagem" rows="3"></textarea>
  </div>

  <div class="mochila">
    <textarea id="mochila" placeholder="Mochila / Itens" rows="3"></textarea>
  </div>

  <div class="btns-salvar">
    <button onclick="salvarFicha()">💾 Salvar Ficha</button>
    <button onclick="carregarFicha()">🔁 Restaurar Ficha</button>
  </div>
</div>

<script>
  function selecionarPersonagem(nome) {
    const audio = document.getElementById("audio");
    const ficha = document.getElementById("fichaBox");
    audio.pause();
    audio.currentTime = 0;

    if (nome === "roxo") {
      ficha.className = "ficha tema-roxo";
      audio.src = "roxo.mp3";
    } else if (nome === "branco") {
      ficha.className = "ficha tema-branco";
      audio.src = "flora.mp3";
    } else if (nome === "preto") {
      ficha.className = "ficha tema-preto";
      audio.src = "sussurros.mp3";
    }

    audio.play();
  }

  function rolarComPonto(btn) {
    const input = btn.previousElementSibling;
    const pontos = parseInt(input.value) || 0;
    const dado = Math.floor(Math.random() * 6) + 1;
    alert(`D6: ${dado} + ${pontos} = ${dado + pontos}`);
  }

  function salvarFicha() {
    const inputs = document.querySelectorAll(".ficha input, .ficha textarea");
    const data = {};
    inputs.forEach(input => {
      if (input.id) data[input.id] = input.value;
    });
    const profs = document.querySelectorAll(".prof input");
    data.profs = Array.from(profs).map(p => p.value);
    localStorage.setItem("fichaRPG", JSON.stringify(data));
    alert("Ficha salva!");
  }

  function carregarFicha() {
    const data = JSON.parse(localStorage.getItem("fichaRPG"));
    if (!data) return alert("Nenhuma ficha salva.");
    for (let key in data) {
      if (key === "profs") continue;
      const el = document.getElementById(key);
      if (el) el.value = data[key];
    }
    const profs = document.querySelectorAll(".prof input");
    profs.forEach((p, i) => {
      if (data.profs && data.profs[i]) p.value = data.profs[i];
    });
    alert("Ficha carregada!");
  }
  
</script>

</body>
</html>
