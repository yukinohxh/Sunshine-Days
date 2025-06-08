<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sunshine Days - Loading</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="loading-screen">
    <div class="loading-text" id="loading-text">loading...</div>
    <button id="start-btn" class="hidden">Start</button>
  </div>

<script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sunshine Days</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="loading-screen">
    <div class="loading-text" id="loading-text">loading...</div>
    <button id="start-btn" class="hidden">Start</button>
  </div>

  <div class="main-content hidden">
    <div class="background"></div>
    <h1>Welcome to Sunshine Days ✨</h1>
    <p>Select your language to continue:</p>
    <select id="lang-select">
      <option value="en">English</option>
      <option value="fr">Français</option>
      <option value="ja">日本語</option>
      <option value="es">Español</option>
    </select>
  </div>

  <script src="script.js"></script>
</body>
</html>

/* RESET DE BASE */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body, html {
  width: 100%;
  height: 100%;
  font-family: 'Comic Sans MS', cursive, sans-serif;
  overflow: hidden;
}

/* --- ÉCRAN DE CHARGEMENT --- */
.loading-screen {
  position: fixed;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #ffaad4, #ffd6f0);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  z-index: 10;
}

.loading-text {
  font-size: 2.5rem;
  color: white;
  animation: fadeInOut 1.4s infinite;
  text-shadow: 2px 2px 5px #ff6fb4;
}

#start-btn {
  margin-top: 30px;
  padding: 12px 25px;
  font-size: 1.2rem;
  background-color: white;
  color: #ff69b4;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  box-shadow: 2px 2px 6px rgba(0,0,0,0.2);
  transition: transform 0.2s, background-color 0.2s;
}

#start-btn:hover {
  background-color: #ffe0f0;
  transform: scale(1.05);
}

.hidden {
  display: none !important;
}

/* --- PAGE PRINCIPALE --- */
.main-content {
  width: 100%;
  height: 100%;
  background-image: url("https://wallpapercave.com/wp/wp2818617.jpg"); /* Prairie Windows XP */
  background-size: cover;
  background-position: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: #fff;
  text-shadow: 2px 2px 4px #000;
  padding: 20px;
}

.main-content h1 {
  font-size: 3rem;
  margin-bottom: 10px;
}

.main-content p {
  font-size: 1.4rem;
  margin-bottom: 20px;
}

#lang-select {
  padding: 10px;
  font-size: 1rem;
  border-radius: 10px;
  border: none;
  background: rgba(255, 255, 255, 0.85);
  color: #333;
  cursor: pointer;
}

/* --- ANIMATIONS --- */
@keyframes fadeInOut {
  0% { opacity: 0.2; }
  50% { opacity: 1; }
  100% { opacity: 0.2; }
}

/* --- ÉTOILES DE CLIC --- */
.star {
  position: absolute;
  width: 12px;
  height: 12px;
  background: white;
  border-radius: 50%;
  pointer-events: none;
  animation: sparkle 0.6s ease-out forwards;
  box-shadow: 0 0 10px #fff;
}

@keyframes sparkle {
  from {
    transform: scale(1);
    opacity: 1;
  }
  to {
    transform: scale(2.5);
    opacity: 0;
  }
}
const loadingText = document.getElementById("loading-text");
const startBtn = document.getElementById("start-btn");
const loadingScreen = document.querySelector(".loading-screen");
const mainContent = document.querySelector(".main-content");

const loadingWords = ["loading...", "chargement...", "読み込み中...", "cargando..."];
let index = 0;

function cycleLoadingText() {
  loadingText.textContent = loadingWords[index];
  index = (index + 1) % loadingWords.length;
}

setInterval(cycleLoadingText, 1500);

// Après 6 secondes on affiche le bouton Start
setTimeout(() => {
  startBtn.classList.remove("hidden");
}, 6000);

// Quand on clique sur Start
startBtn.addEventListener("click", () => {
  loadingScreen.classList.add("hidden");
  mainContent.classList.remove("hidden");
});

// Étoile quand tu cliques
document.addEventListener("click", (e) => {
  const star = document.createElement("div");
  star.classList.add("star");
  star.style.left = `${e.pageX}px`;
  star.style.top = `${e.pageY}px`;
  document.body.appendChild(star);

  setTimeout(() => {
    star.remove();
  }, 600);
});
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sunshine Days</title>
  <link rel="stylesheet" href="style.css" />
  <script defer src="script.js"></script>
</head>
<body>
  <div id="loading-screen">
    <div id="loading-text">Loading...</div>
    <button id="start-button" style="display:none;">Start</button>
  </div>

  <main id="main-content" style="display:none;">
    <!-- Menu principal -->
    <header>
      <h1>🌞 Sunshine Days</h1>
      <nav>
        <button class="nav-btn" data-section="about">About</button>
        <button class="nav-btn" data-section="characters">Characters</button>
        <button class="nav-btn" data-section="extras">Extras</button>
        <button class="nav-btn" data-section="funfact">Fun Fact of the Day</button>
        <button class="nav-btn" data-section="media">Media</button>
      </nav>
    </header>

    <!-- Sections -->
    <section id="about" class="content-section">
      <!-- Will be filled dynamically or manually later -->
    </section>

    <section id="characters" class="content-section">
      <!-- Personnages -->
    </section>

    <section id="extras" class="content-section">
      <!-- Infos anime, autrice, voix, etc. -->
    </section>

    <section id="funfact" class="content-section">
      <h2>✨ Fun Fact of the Day ✨</h2>
      <p id="daily-fact">Coming soon...</p>
    </section>

    <section id="media" class="content-section">
      <h2>🎨 Media Gallery</h2>
      <p>Fanarts & GIFs below</p>
      <div id="fanart-gallery"></div>
      <p>If you want your fanart featured, DM me on Discord: <strong>yxv.lxc</strong></p>
    </section>
  </main>
</body>
</html>
/* style.css */
body {
  margin: 0;
  font-family: "Poppins", sans-serif;
  background: url('https://wallpapercave.com/wp/wp2512032.jpg') no-repeat center center fixed;
  background-size: cover;
  color: #333;
}

#loading-screen {
  position: fixed;
  width: 100%;
  height: 100vh;
  background: linear-gradient(135deg, #fbd3e9, #bb377d);
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-size: 2rem;
  z-index: 1000;
  color: white;
}

#start-button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 1.2rem;
  border: none;
  background: white;
  color: #bb377d;
  cursor: pointer;
  border-radius: 10px;
}

header {
  background: rgba(255, 255, 255, 0.9);
  padding: 1em;
  text-align: center;
  border-bottom: 2px solid #ccc;
}

nav {
  display: flex;
  justify-content: center;
  gap: 1em;
  margin-top: 0.5em;
}

.nav-btn {
  background: #ffb6c1;
  border: none;
  padding: 0.5em 1em;
  border-radius: 12px;
  cursor: pointer;
  font-weight: bold;
}

.content-section {
  padding: 2em;
  display: none;
}

.content-section.active {
  display: block;
}
// script.js
const messages = ["Loading...", "Chargement...", "読み込み中...", "Cargando..."];
let current = 0;
const loadingText = document.getElementById("loading-text");
const startButton = document.getElementById("start-button");

setInterval(() => {
  current = (current + 1) % messages.length;
  loadingText.textContent = messages[current];
}, 1500);

setTimeout(() => {
  startButton.style.display = "block";
}, 5000);

startButton.addEventListener("click", () => {
  document.getElementById("loading-screen").style.display = "none";
  document.getElementById("main-content").style.display = "block";
});

// Navigation simple
document.querySelectorAll(".nav-btn").forEach((btn) => {
  btn.addEventListener("click", () => {
    document.querySelectorAll(".content-section").forEach((section) => {
      section.classList.remove("active");
    });
    document.getElementById(btn.dataset.section).classList.add("active");
  });
});
<!-- À insérer dans <section id="about"> -->
<h2>📝 About Sunshine Days</h2>

<h3>🌼 What is Sunshine Days?</h3>
<p>
  <strong>Sunshine Days</strong> is a magical girl anime created in 2007 by a young indie creator known under the pseudonym <em>Himari Kurosawa</em>. Inspired by series like *Smile Precure* and her own personal life, the anime follows a group of girls who gain magical powers and fight to bring hope and color to a fading world.
</p>

<h3>💡 Creation & Themes</h3>
<ul>
  <li>Created in: <strong>2007</strong></li>
  <li>Main inspirations: <em>Smile Precure, real-life trauma & healing, LGBTQ+ themes</em></li>
  <li>Language: <strong>Japanese (original)</strong>, with fan translations in English, French, and Spanish</li>
  <li>What makes it special? It features <strong>trans characters</strong>, <strong>mental health metaphors</strong>, and a deliberately soft, dreamy art style.</li>
</ul>

<h3>👩‍🎨 About the Creator</h3>
<p>
  The anime was entirely written, drawn, and directed by <strong>Himari Kurosawa</strong>, a mysterious indie artist who used only pseudonyms online. Many of the characters were voiced by her close friends, each represented by unique online nicknames.
</p>

<h3>🔮 Legacy</h3>
<p>
  Although it never got a major commercial release, *Sunshine Days* became a cult classic in online spaces. Some episodes are now considered <strong>lost media</strong>, and fans continue to archive, draw, and share everything they can find.
</p>
<!-- À insérer dans <section id="characters"> -->
<h2>🌟 Main Characters</h2>

<div class="character-card">
  <h3>🌸 Momoka</h3>
  <p>
    A bright, optimistic girl who serves as the heart of the team. She represents <strong>hope</strong> and is one of the most beloved characters. Her design was based on the creator’s childhood friend.
  </p>
</div>

<div class="character-card">
  <h3>🔵 Sora</h3>
  <p>
    Mysterious and cool-headed, Sora originally was meant to be shipped with Miyuu, but eventually got paired with Momoka. Many fans admire his gentle but powerful nature.
  </p>
</div>

<div class="character-card">
  <h3>🍃 Hina & Miyuu</h3>
  <p>
    A canon lesbian couple. Hina is shy and smart while Miyuu is cheerful and energetic. Their love is central to the second season.
  </p>
</div>

<div class="character-card">
  <h3>🌊 Goddess of the Sea & Goddess of the Forest</h3>
  <p>
    Divine beings representing nature. The creator secretly shipped them together and adored both of them. They appear as guardians in the final arc.
  </p>
</div>
<!-- À insérer dans <section id="media"> -->
<h2>🖼️ Fanart Gallery</h2>
<div class="fanart-gallery">
  <img src="images/fanart1.gif" alt="Momoka GIF" />
  <img src="images/fanart2.png" alt="Sora and Momoka" />
  <!-- Tu peux continuer à rajouter autant d’images que tu veux ici -->
</div>

<p class="fanart-note">
  Want your fanart featured here? DM me on Discord: <strong>yxv.lxc</strong>our server is coming soon!
</p>
.fanart-gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 1em;
}

.fanart-gallery img {
  width: 200px;
  border-radius: 10px;
  box-shadow: 0 0 10px #00000040;
}

.fanart-note {
  margin-top: 1em;
  font-style: italic;
}
.star {
  position: absolute;
  font-size: 24px;
  color: #fff;
  text-shadow: 0 0 10px pink;
  animation: sparkle 1s forwards;
}

@keyframes sparkle {
  0% { opacity: 1; transform: scale(1); }
  100% { opacity: 0; transform: scale(2) translateY(-30px); }
}
document.body.addEventListener("click", function (e) {
  const star = document.createElement("div");
  star.classList.add("star");
  star.textContent = "✨";
  star.style.left = e.pageX + "px";
  star.style.top = e.pageY + "px";
  document.body.appendChild(star);
  setTimeout(() => star.remove(), 1000);
});
<div id="language-selector">
  <span>Select Language:</span>
  <button data-lang="en">🇬🇧</button>
  <button data-lang="fr">🇫🇷</button>
  <button data-lang="ja">🇯🇵</button>
  <button data-lang="es">🇪🇸</button>
  <button data-lang="ru">🇷🇺</button>
</div>
#language-selector {
  position: fixed;
  top: 15px;
  right: 15px;
  background: #fff0f6;
  border: 2px solid #ffb6c1;
  border-radius: 12px;
  padding: 10px 15px;
  font-family: 'Comic Sans MS', cursive;
  box-shadow: 0 0 10px #ffb6c1;
  z-index: 9999;
}

#language-selector span {
  margin-right: 10px;
  font-weight: bold;
  color: #d6336c;
}

#language-selector button {
  background: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
  transition: transform 0.2s;
}

#language-selector button:hover {
  transform: scale(1.2);
}
<script>
const translations = {
  en: {
    siteTitle: "Sunshine Days",
    aboutTitle: "About Sunshine Days",
    whatIs: "What is Sunshine Days?",
    creationThemes: "Creation & Themes",
    aboutCreator: "About the Creator",
    legacy: "Legacy",
    charactersTitle: "Main Characters",
    fanartGallery: "Fanart Gallery",
    fanartNote: "Want your fanart featured here? DM me on Discord: yxv.lxc"
  },
  fr: {
    siteTitle: "Jours Ensoleillés",
    aboutTitle: "À propos de Sunshine Days",
    whatIs: "Qu'est-ce que Sunshine Days ?",
    creationThemes: "Création & Thèmes",
    aboutCreator: "À propos de l'autrice",
    legacy: "Héritage",
    charactersTitle: "Personnages Principaux",
    fanartGallery: "Galerie de Fanarts",
    fanartNote: "Tu veux que ton fanart apparaisse ici ? Contacte-moi sur Discord : yxv.lxc"
  },
  ja: {
    siteTitle: "サンシャインデイズ",
    aboutTitle: "サンシャインデイズについて",
    whatIs: "サンシャインデイズとは？",
    creationThemes: "制作とテーマ",
    aboutCreator: "作者について",
    legacy: "遺産",
    charactersTitle: "主要キャラクター",
    fanartGallery: "ファンアートギャラリー",
    fanartNote: "あなたのファンアートを掲載したい？Discordで連絡してね：yxv.lxc"
  },
  es: {
    siteTitle: "Días de Sol",
    aboutTitle: "Sobre Sunshine Days",
    whatIs: "¿Qué es Sunshine Days?",
    creationThemes: "Creación y Temas",
    aboutCreator: "Sobre la Creadora",
    legacy: "Legado",
    charactersTitle: "Personajes Principales",
    fanartGallery: "Galería de Fanart",
    fanartNote: "¿Quieres que tu fanart aparezca aquí? Contáctame en Discord: yxv.lxc"
  },
  ru: {
    siteTitle: "Солнечные Дни",
    aboutTitle: "О Sunshine Days",
    whatIs: "Что такое Sunshine Days?",
    creationThemes: "Создание и Темы",
    aboutCreator: "Об Авторе",
    legacy: "Наследие",
    charactersTitle: "Главные Персонажи",
    fanartGallery: "Галерея Фанартов",
    fanartNote: "Хочешь, чтобы твой фанарт был здесь? Напиши мне в Discord: yxv.lxc"
  }
};

const changeLanguage = (lang) => {
  const t = translations[lang];
  document.title = t.siteTitle;
  document.getElementById("about-title").textContent = t.aboutTitle;
  document.getElementById("what-is").textContent = t.whatIs;
  document.getElementById("creation-themes").textContent = t.creationThemes;
  document.getElementById("about-creator").textContent = t.aboutCreator;
  document.getElementById("legacy").textContent = t.legacy;
  document.getElementById("characters-title").textContent = t.charactersTitle;
  document.getElementById("fanart-gallery").textContent = t.fanartGallery;
  document.getElementById("fanart-note").textContent = t.fanartNote;
};

document.querySelectorAll('#language-selector button').forEach(btn => {
  btn.addEventListener('click', () => changeLanguage(btn.dataset.lang));
});
</script>
<h2 id="about-title">📝 About Sunshine Days</h2>
<h3 id="what-is">🌼 What is Sunshine Days?</h3>
<h3 id="creation-themes">💡 Creation & Themes</h3>
<h3 id="about-creator">👩‍🎨 About the Creator</h3>
<h3 id="legacy">🔮 Legacy</h3>

<h2 id="characters-title">🌟 Main Characters</h2>

<h2 id="fanart-gallery">🖼️ Fanart Gallery</h2>
<p id="fanart-note" class="fanart-note">
  Want your fanart featured here? DM me on Discord: <strong>yxv.lxc</strong>
</p>

