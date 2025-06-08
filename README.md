<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>🌈 SunshineShrine - Fan Social Network for Sunshine Days ✨</title>
<style>
  /* === STYLE ULTRA CUTEORE PIXEL === */
  @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

  * {
    box-sizing: border-box;
  }

  body {
    margin:0; padding:0;
    font-family: 'Press Start 2P', cursive;
    background: linear-gradient(135deg, #ffd4e0, #ffc4cc);
    color: #d63384;
    user-select: none;
  }

  header {
    background: url('https://i.pinimg.com/originals/9e/50/9a/9e509a5f74b04eebbb4ee47406f6349d.gif') no-repeat center/cover;
    padding: 40px 10px 30px;
    border-bottom: 6px dashed #f497b2;
    text-align: center;
    color: white;
    text-shadow: 2px 2px 3px #000;
  }
  header h1 {
    font-size: 2.5rem;
    margin: 0;
  }
  header p {
    font-size: 0.8rem;
    margin: 4px 0 0;
    font-style: italic;
    letter-spacing: 1.5px;
  }

  /* Language popup */
  #language-popup {
    position: fixed;
    inset: 0;
    background: rgba(255, 192, 203, 0.9);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 10000;
    user-select:none;
  }
  #language-popup.hidden {
    display: none;
  }
  #language-popup .popup-inner {
    background: #fff0fa;
    border: 5px dotted #d63384;
    padding: 35px 50px;
    border-radius: 16px;
    text-align: center;
    color: #d63384;
  }
  #language-popup select {
    font-family: 'Press Start 2P', cursive;
    font-size: 1rem;
    padding: 8px;
    margin-top: 15px;
    border: 3px dashed #d63384;
    border-radius: 10px;
    background: #ffe6f0;
    color: #d63384;
    cursor: pointer;
  }
  #language-popup button {
    margin-top: 25px;
    font-family: 'Press Start 2P', cursive;
    background: #d63384;
    color: #fff0fa;
    border: none;
    padding: 12px 20px;
    border-radius: 12px;
    cursor: pointer;
    font-size: 0.8rem;
    transition: background 0.3s ease;
  }
  #language-popup button:hover {
    background: #b02462;
  }

  /* NAV BAR */
  nav {
    background: #ffc6d8;
    padding: 10px 0;
    border-bottom: 4px dotted #d63384;
    display: flex;
    justify-content: center;
    gap: 30px;
    font-size: 0.7rem;
  }
  nav a {
    color: #d63384;
    text-decoration: none;
    transition: color 0.3s ease;
  }
  nav a:hover {
    color: #9e1d52;
  }

  /* MAIN AREA */
  main {
    max-width: 900px;
    margin: 20px auto 60px;
    padding: 0 20px;
  }

  /* FYP TITLE */
  #fyp-title {
    text-align: center;
    font-size: 1.3rem;
    margin-bottom: 15px;
    color: #b62f78;
    text-shadow: 1px 1px #fff;
  }

  /* POSTS CONTAINER */
  #posts-container {
    display: flex;
    flex-direction: column;
    gap: 18px;
    min-height: 250px;
  }
  .empty-message {
    color: #b62f78;
    text-align: center;
    font-style: italic;
  }

  /* POST CARD */
  .post {
    background: #ffe6f0;
    border: 3px dashed #d63384;
    border-radius: 12px;
    padding: 15px;
    box-shadow: 4px 4px 10px rgba(198, 55, 101, 0.3);
    position: relative;
  }
  .post .author {
    font-weight: 700;
    color: #9e1d52;
    margin-bottom: 8px;
    cursor: pointer;
  }
  .post .content {
    font-size: 0.8rem;
    margin-bottom: 10px;
    white-space: pre-wrap;
  }
  .post .media {
    margin: 10px 0;
    max-width: 100%;
    border-radius: 8px;
  }
  .post .hashtags {
    font-size: 0.7rem;
    color: #a6306e;
  }
  .post .post-footer {
    display: flex;
    justify-content: space-between;
    font-size: 0.7rem;
    margin-top: 12px;
  }
  .post .post-footer button {
    background: none;
    border: none;
    color: #b62f78;
    cursor: pointer;
    font-family: 'Press Start 2P', cursive;
  }
  .post .post-footer button:hover {
    color: #9e1d52;
  }

  /* COMMENTS */
  .comments-section {
    margin-top: 12px;
    border-top: 1px dotted #d63384;
    padding-top: 10px;
  }
  .comments-section .comment {
    background: #ffd0dc;
    border: 1px solid #d63384;
    border-radius: 6px;
    padding: 6px;
    margin-bottom: 6px;
    font-size: 0.65rem;
    color: #6f1d40;
  }
  .comments-section .comment .c-author {
    font-weight: 700;
  }
  .comment-input {
    margin-top: 6px;
    display: flex;
    gap: 6px;
  }
  .comment-input input {
    flex: 1;
    border: 2px dashed #d63384;
    border-radius: 6px;
    font-family: 'Press Start 2P', cursive;
    font-size: 0.65rem;
    padding: 6px;
    color: #9e1d52;
  }
  .comment-input button {
    padding: 6px 12px;
    background: #d63384;
    color: white;
    font-family: 'Press Start 2P', cursive;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-size: 0.65rem;
  }
  .comment-input button:hover {
    background: #9e1d52;
  }

  /* PROFILE SECTION */
  #profile-section {
    background: #fff0fa;
    border: 4px dotted #d63384;
    border-radius: 20px;
    padding: 20px;
    margin-top: 40px;
    max-width: 700px;
    margin-left: auto;
    margin-right: auto;
  }
  #profile-section h2 {
    text-align: center;
    color: #9e1d52;
  }
  #profile-form label {
    display: block;
    font-size: 0.7rem;
    margin-top: 15px;
    color: #b62f78;
  }
  #profile-form input[type="text"], #profile-form textarea {
    width: 100%;
    padding: 10px;
    font-family: 'Press Start 2P', cursive;
    font-size: 0.7rem;
    border: 3px dashed #d63384;
    border-radius: 12px;
    resize: none;
    background: #ffe6f0;
    color: #9e1d52;
  }
  #profile-form button {
    margin-top: 20px;
    width: 100%;
    background: #d63384;
    color: white;
    border: none;
    font-family: 'Press Start 2P', cursive;
    font-size: 0.8rem;
    padding: 14px 0;
    border-radius: 20px;
    cursor: pointer;
  }
  #profile-form button:hover {
    background: #9e1d52;
  }
  #profile-banner {
    width: 100%;
    height: 120px;
    object-fit: cover;
    border-radius: 12px;
    margin-top: 15px;
    border: 3px dashed #d63384;
  }

  /* POST CREATION FORM */
  #post-creation {
    background: #fff0fa;
    border: 4px dotted #d63384;
    border-radius: 16px;
    padding: 20px;
    margin: 40px auto;
    max-width: 700px;
  }
  #post-creation h2 {
    color: #9e1d52;
    text-align: center;
  }
  #post-creation textarea {
    width: 100%;
    height: 90px;
    border: 3px dashed #d63384;
    border-radius: 12px;
    font-family: 'Press Start 2P', cursive;
    font-size: 0.7rem;
    padding: 12px;
    resize: none;
    color: #9e1d52;
    background: #ffe6f0;
  }
  #post-creation input[type="text"] {
    width: 100%;
    padding: 10px;
    font-family: 'Press Start 2P', cursive;
    font-size: 0.7rem;
    margin-top: 12px;
    border: 3px dashed #d63384;
    border-radius: 12px;
    background: #ffe6f0;
    color: #9e1d52;
  }
  #post-creation input[type="file"] {
    margin-top: 12px;
  }
  #post-creation button {
    margin-top: 20px;
    background: #d63384;
    color: white;
    border: none;
    font-family: 'Press Start 2P', cursive;
    font-size: 0.8rem;
    padding: 14px 0;
    width: 100%;
    border-radius: 20px;
    cursor: pointer;
  }
  #post-creation button:hover {
    background: #9e1d52;
  }

  /* USER LIST & FOLLOW */
  #users-list {
    max-width: 700px;
    margin: 30px auto;
    background: #fff0fa;
    border: 4px dotted #d63384;
    border-radius: 20px;
    padding: 20px;
  }
  #users-list h3 {
    color: #9e1d52;
    text-align: center;
  }
  .user-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 2px dashed #d63384;
    padding: 10px 0;
    font-size: 0.7rem;
    color: #b62f78;
  }
  .user-item button {
    font-family: 'Press Start 2P', cursive;
    background: #d63384;
    border: none;
    color: white;
    border-radius: 12px;
    padding: 6px 12px;
    cursor: pointer;
    transition: background 0.3s ease;
  }
  .user-item button:hover {
    background: #9e1d52;
  }

  /* MESSAGES */
  #messages-section {
    max-width: 700px;
    margin: 30px auto 80px;
    background: #fff0fa;
    border: 4px dotted #d63384;
    border-radius: 20px;
    padding: 20px;
  }
  #messages-section h3 {
    color: #9e1d52;
    text-align: center;
  }
  #messages-list {
    max-height: 250px;
    overflow-y: auto;
    border: 2px dashed #d63384;
    background: #ffe6f0;
    padding: 10px;
    border-radius: 12px;
    font-size: 0.7rem;
    color: #9e1d52;
  }
  .message-item {
    margin-bottom: 10px;
  }
  .message-author {
    font-weight: 700;
    color: #b62f78;
  }
  #message-form {
    margin-top: 15px;
    display: flex;
    gap: 8px;
  }
  #message-form select, #message-form input[type="text"] {
    font-family: 'Press Start 2P', cursive;
    font-size: 0.7rem;
    padding: 8px;
    border: 3px dashed #d63384;
    border-radius: 12px;
    background: #ffe6f0;
    color: #9e1d52;
  }
  #message-form input[type="text"] {
    flex: 1;
  }
  #message-form button {
    background: #d63384;
    color: white;
    font-family: 'Press Start 2P', cursive;
    border: none;
    border-radius: 12px;
    padding: 8px 16px;
    cursor: pointer;
  }
  #message-form button:hover {
    background: #9e1d52;
  }

  /* FOOTER */
  footer {
    text-align: center;
    margin-bottom: 40px;
    font-size: 0.6rem;
    color: #b62f78;
    font-family: 'Press Start 2P', cursive;
  }

  /* Responsive */
  @media (max-width: 600px) {
    nav {
      gap: 15px;
      font-size: 0.6rem;
    }
    #post-creation textarea {
      height: 70px;
    }
  }
</style>
</head>
<body>

<header>
  <h1>🌞 SunshineShrine</h1>
  <p>The Official Fan Social Network for Sunshine Days ✨</p>
</header>

<div id="language-popup" aria-label="Choose Language">
  <div class="popup-inner">
    <h2>Select Your Language / Sélectionnez votre langue</h2>
    <select id="language-select" aria-label="Language selection">
      <option value="en" selected>English</option>
      <option value="fr">Français</option>
      <option value="ja">日本語</option>
      <option value="es">Español</option>
      <option value="de">Deutsch</option>
    </select>
    <br />
    <button id="lang-confirm-btn">Confirm / Confirmer</button>
  </div>
</div>

<nav aria-label="Main navigation">
  <a href="#" data-section="feed" class="nav-link active">Feed</a>
  <a href="#" data-section="profile" class="nav-link">My Profile</a>
  <a href="#" data-section="users" class="nav-link">Users</a>
  <a href="#" data-section="messages" class="nav-link">Messages</a>
</nav>

<main>

  <!-- FEED SECTION -->
  <section id="feed-section" aria-label="Feed" tabindex="0">
    <h2 id="fyp-title">Your Sunshine Feed</h2>

    <div id="post-creation" aria-label="Create a new post">
      <h2>Create New Post</h2>
      <textarea id="new-post-content" placeholder="Write your post here..."></textarea>
      <input type="text" id="new-post-hashtags" placeholder="Add hashtags separated by spaces (#sunshine #love)" />
      <input type="file" id="new-post-media" accept="image/*,video/*" aria-label="Upload image or video (optional)" />
      <button id="create-post-btn">Post It!</button>
    </div>

    <div id="posts-container" aria-live="polite" aria-relevant="additions"></div>
  </section>

  <!-- PROFILE SECTION -->
  <section id="profile-section" aria-label="User Profile" tabindex="0" hidden>
    <h2>My Profile</h2>
    <form id="profile-form" aria-describedby="profile-desc">
      <label for="profile-username">Username (max 12 chars)</label>
      <input type="text" id="profile-username" maxlength="12" required placeholder="Your cool name" />

      <label for="profile-bio">Bio (max 100 chars)</label>
      <textarea id="profile-bio" maxlength="100" rows="3" placeholder="Say something cute or epic..."></textarea>

      <label for="profile-banner-url">Banner Image URL (optional)</label>
      <input type="text" id="profile-banner-url" placeholder="Paste a URL for your profile banner" />

      <img id="profile-banner" alt="Profile banner preview" src="" hidden />

      <button type="submit">Save Profile</button>
    </form>
  </section>

  <!-- USERS LIST SECTION -->
  <section id="users-section" aria-label="Users List" tabindex="0" hidden>
    <h3>Users Around the World</h3>
    <div id="users-list"></div>
  </section>

  <!-- MESSAGES SECTION -->
  <section id="messages-section" aria-label="Private Messages" tabindex="0" hidden>
    <h3>Private Messages</h3>

    <div id="messages-list" aria-live="polite" aria-relevant="additions"></div>

    <form id="message-form" aria-label="Send private message">
      <select id="message-recipient" aria-label="Select recipient"></select>
      <input type="text" id="message-input" placeholder="Type your message..." required autocomplete="off" />
      <button type="submit">Send</button>
    </form>
  </section>

</main>

<footer>
  © 2025 SunshineShrine — Created by Yukino | Powered by Love & Code 💖
</footer>

<script>
  // === DATA & STORAGE ===
  const STORAGE_KEY = 'sunshineshrine_data_v1';

  // Default empty data structure
  let data = {
    users: [],
    posts: [],
    messages: [],
    currentUser: null,
    lang: 'en'
  };

  // === LANGUAGE STRINGS ===
  const i18n = {
    en: {
      feedTitle: "Your Sunshine Feed",
      createPost: "Create New Post",
      placeholderPost: "Write your post here...",
      placeholderHashtags: "Add hashtags separated by spaces (#sunshine #love)",
      placeholderMedia: "Upload image or video (optional)",
      postIt: "Post It!",
      profile: "My Profile",
      users: "Users",
      messages: "Messages",
      usernameLabel: "Username (max 12 chars)",
      bioLabel: "Bio (max 100 chars)",
      bannerLabel: "Banner Image URL (optional)",
      saveProfile: "Save Profile",
      usersListTitle: "Users Around the World",
      privateMessages: "Private Messages",
      selectRecipient: "Select recipient",
      messagePlaceholder: "Type your message...",
      sendBtn: "Send",
      emptyPosts: "No posts yet, be the first to shine!",
      emptyUsers: "No other users yet, create your profile!",
      emptyMessages: "No messages yet",
      commentPlaceholder: "Write a comment...",
      commentBtn: "Comment",
      languagePopupTitle: "Select Your Language / Sélectionnez votre langue",
      langConfirmBtn: "Confirm / Confirmer"
    },
    fr: {
      feedTitle: "Votre Fil Sunshine",
      createPost: "Créer un Nouveau Post",
      placeholderPost: "Écris ton post ici...",
      placeholderHashtags: "Ajoute des hashtags séparés par des espaces (#soleil #amour)",
      placeholderMedia: "Télécharge une image ou vidéo (optionnel)",
      postIt: "Poster !",
      profile: "Mon Profil",
      users: "Utilisateurs",
      messages: "Messages",
      usernameLabel: "Pseudo (max 12 caractères)",
      bioLabel: "Bio (max 100 caractères)",
      bannerLabel: "URL de l'image de bannière (optionnel)",
      saveProfile: "Sauvegarder Profil",
      usersListTitle: "Utilisateurs autour du monde",
      privateMessages: "Messages Privés",
      selectRecipient: "Choisir un destinataire",
      messagePlaceholder: "Écris ton message...",
      sendBtn: "Envoyer",
      emptyPosts: "Aucun post pour le moment, sois le premier à briller !",
      emptyUsers: "Pas d'autres utilisateurs, crée ton profil !",
      emptyMessages: "Pas encore de messages",
      commentPlaceholder: "Écris un commentaire...",
      commentBtn: "Commenter",
      languagePopupTitle: "Sélectionnez votre langue / Select Your Language",
      langConfirmBtn: "Confirmer / Confirm"
    }
  };

  // === DOM ELEMENTS ===
  const langPopup = document.getElementById('language-popup');
  const langSelect = document.getElementById('language-select');
  const langConfirmBtn = document.getElementById('lang-confirm-btn');

  const navLinks = document.querySelectorAll('.nav-link');
  const feedSection = document.getElementById('feed-section');
  const profileSection = document.getElementById('profile-section');
  const usersSection = document.getElementById('users-section');
  const messagesSection = document.getElementById('messages-section');

  const postsContainer = document.getElementById('posts-container');
  const usersList = document.getElementById('users-list');
  const messagesList = document.getElementById('messages-list');

  const profileForm = document.getElementById('profile-form');
  const profileUsername = document.getElementById('profile-username');
  const profileBio = document.getElementById('profile-bio');
  const profileBannerUrl = document.getElementById('profile-banner-url');
  const profileBanner = document.getElementById('profile-banner');

  const messageForm = document.getElementById('message-form');
  const messageRecipient = document.getElementById('message-recipient');
  const messageInput = document.getElementById('message-input');

  const newPostContent = document.getElementById('new-post-content');
  const newPostHashtags = document.getElementById('new-post-hashtags');
  const newPostMedia = document.getElementById('new-post-media');
  const createPostBtn = document.getElementById('create-post-btn');

  // === FUNCTIONS ===

  // Load data from localStorage
  function loadData() {
    const savedData = localStorage.getItem(STORAGE_KEY);
    if (savedData) {
      data = JSON.parse(savedData);
    }
  }

  // Save data to localStorage
  function saveData() {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
  }

  // Update UI language strings
  function updateLanguageUI() {
    const lang = data.lang;
    document.getElementById('fyp-title').textContent = i18n[lang].feedTitle;
    document.querySelector('#post-creation h2').textContent = i18n[lang].createPost;
    newPostContent.placeholder = i18n[lang].placeholderPost;
    newPostHashtags.placeholder = i18n[lang].placeholderHashtags;
    newPostMedia.setAttribute('aria-label', i18n[lang].placeholderMedia);
    createPostBtn.textContent = i18n[lang].postIt;
    document.querySelector('nav a[data-section="profile"]').textContent = i18n[lang].profile;
    document.querySelector('nav a[data-section="users"]').textContent = i18n[lang].users;
    document.querySelector('nav a[data-section="messages"]').textContent = i18n[lang].messages;
    document.querySelector('#profile-section h2').textContent = i18n[lang].profile;
    document.querySelector('label[for="profile-username"]').textContent = i18n[lang].usernameLabel;
    document.querySelector('label[for="profile-bio"]').textContent = i18n[lang].bioLabel;
    document.querySelector('label[for="profile-banner-url"]').textContent = i18n[lang].bannerLabel;
    profileForm.querySelector('button[type="submit"]').textContent = i18n[lang].saveProfile;
    document.querySelector('#users-section h3').textContent = i18n[lang].usersListTitle;
    document.querySelector('#messages-section h3').textContent = i18n[lang].privateMessages;
    messageRecipient.options.length = 0;
    data.users.forEach(user => {
      if (user.username !== data.currentUser) {
        const option = document.createElement('option');
        option.value = user.username;
        option.textContent = user.username;
        messageRecipient.appendChild(option);
      }
    });
    messageInput.placeholder = i18n[lang].messagePlaceholder;
    messageForm.querySelector('button[type="submit"]').textContent = i18n[lang].sendBtn;
  }

  // Show only the selected section
  function showSection(section) {
    feedSection.hidden = true;
    profileSection.hidden = true;
    usersSection.hidden = true;
    messagesSection.hidden = true;

    document.querySelectorAll('.nav-link').forEach(link => {
      link.classList.remove('active');
    });

    if (section === 'feed') {
      feedSection.hidden = false;
      document.querySelector('.nav-link[data-section="feed"]').classList.add('active');
    } else if (section === 'profile') {
      profileSection.hidden = false;
      document.querySelector('.nav-link[data-section="profile"]').classList.add('active');
    } else if (section === 'users') {
      usersSection.hidden = false;
      document.querySelector('.nav-link[data-section="users"]').classList.add('active');
    } else if (section === 'messages') {
      messagesSection.hidden = false;
      document.querySelector('.nav-link[data-section="messages"]').classList.add('active');
    }
  }

  // Render posts to UI
  function renderPosts() {
    postsContainer.innerHTML = '';
    if (data.posts.length === 0) {
      const emptyMsg = document.createElement('p');
      emptyMsg.textContent = i18n[data.lang].emptyPosts;
      postsContainer.appendChild(emptyMsg);
      return;
    }
    data.posts.forEach(post => {
      const postDiv = document.createElement('div');
      postDiv.className = 'post-item';
      const user = data.users.find(u => u.username === post.author);
      const userDisplayName = user ? user.username : 'Unknown';

      postDiv.innerHTML = `
        <p><strong>${userDisplayName}</strong>: ${post.content}</p>
        ${post.media ? `<img src="${post.media}" alt="Post media" style="max-width: 100%; border-radius: 8px;" />` : ''}
        <p class="hashtags">${post.hashtags.join(' ')}</p>
      `;
      postsContainer.appendChild(postDiv);
    });
  }

  // Render users list to UI
  function renderUsers() {
    usersList.innerHTML = '';
    if (data.users.length === 0) {
      const emptyMsg = document.createElement('p');
      emptyMsg.textContent = i18n[data.lang].emptyUsers;
      usersList.appendChild(emptyMsg);
      return;
    }
    data.users.forEach(user => {
      const userDiv = document.createElement('div');
      userDiv.className = 'user-item';
      userDiv.innerHTML = `
        <p><strong>${user.username}</strong></p>
        <p>${user.bio}</p>
      `;
      usersList.appendChild(userDiv);
    });
  }

  // Render messages list to UI
  function renderMessages() {
    messagesList.innerHTML = '';
    const userMessages = data.messages.filter(m => 
      m.sender === data.currentUser || m.recipient === data.currentUser);
    if (userMessages.length === 0) {
      const emptyMsg = document.createElement('p');
      emptyMsg.textContent = i18n[data.lang].emptyMessages;
      messagesList.appendChild(emptyMsg);
      return;
    }
    userMessages.forEach(msg => {
      const msgDiv = document.createElement('div');
      msgDiv.className = 'message-item';
      msgDiv.innerHTML = `
        <span class="message-author">${msg.sender} → ${msg.recipient}:</span> ${msg.content}
      `;
      messagesList.appendChild(msgDiv);
    });
  }

  // === EVENT LISTENERS ===

  // Language confirmation popup
  langConfirmBtn.addEventListener('click', () => {
    data.lang = langSelect.value;
    updateLanguageUI();
    langPopup.style.display = 'none';
    saveData();
  });

  // Navigation
  navLinks.forEach(link => {
    link.addEventListener('click', (e) => {
      e.preventDefault();
      const section = e.target.getAttribute('data-section');
      showSection(section);
    });
  });

  // Profile form submission
  profileForm.addEventListener('submit', (e) => {
    e.preventDefault();
    const username = profileUsername.value.trim();
    const bio = profileBio.value.trim();
    const bannerUrl = profileBannerUrl.value.trim();

    if (username.length === 0 || username.length > 12) {
      alert('Username must be between 1 and 12 characters!');
      return;
    }
    if (bio.length > 100) {
      alert('Bio must be 100 characters max!');
      return;
    }

    // Check if username already exists (except current user)
    const usernameExists = data.users.some(u => u.username === username && username !== data.currentUser);
    if (usernameExists) {
      alert('Username already taken!');
      return;
    }

    // If new user, add to users list
    if (!data.currentUser) {
      data.currentUser = username;
      data.users.push({ username, bio, bannerUrl });
    } else {
      // Update existing user info
      const currentUserIndex = data.users.findIndex(u => u.username === data.currentUser);
      if (currentUserIndex !== -1) {
        data.users[currentUserIndex].username = username;
        data.users[currentUserIndex].bio = bio;
        data.users[currentUserIndex].bannerUrl = bannerUrl;
      }
      data.currentUser = username;
    }

    saveData();
    updateLanguageUI();
    renderUsers();
    alert('Profile saved successfully!');
  });

  // Profile banner preview update
  profileBannerUrl.addEventListener('input', () => {
    const url = profileBannerUrl.value.trim();
    if (url) {
      profileBanner.src = url;
      profileBanner.hidden = false;
    } else {
      profileBanner.hidden = true;
    }
  });

  // Create post button click
  createPostBtn.addEventListener('click', () => {
    const content = newPostContent.value.trim();
    const hashtags = newPostHashtags.value.trim().split(' ').filter(tag => tag.startsWith('#'));
    const file = newPostMedia.files[0];
    if (!content) {
      alert('Post content cannot be empty!');
      return;
    }

    if (file) {
      const reader = new FileReader();
      reader.onload = () => {
        const mediaUrl = reader.result;
        data.posts.push({
          author: data.currentUser,
          content,
          hashtags,
          media: mediaUrl
        });
        saveData();
        renderPosts();
        newPostContent.value = '';
        newPostHashtags.value = '';
        newPostMedia.value = '';
        alert('Post created!');
      };
      reader.readAsDataURL(file);
    } else {
      data.posts.push({
        author: data.currentUser,
        content,
        hashtags,
        media: null
      });
      saveData();
      renderPosts();
      newPostContent.value = '';
      newPostHashtags.value = '';
      newPostMedia.value = '';
      alert('Post created!');
    }
  });

  // Send private message
  messageForm.addEventListener('submit', (e) => {
    e.preventDefault();
    const recipient = messageRecipient.value;
    const content = messageInput.value.trim();
    if (!recipient) {
      alert('Select a recipient!');
      return;
    }
    if (!content) {
      alert('Message cannot be empty!');
      return;
    }
    data.messages.push({
      sender: data.currentUser,
      recipient,
      content
    });
    saveData();
    renderMessages();
    messageInput.value = '';
    alert('Message sent!');
  });

  // Initial load
  loadData();
  if (!data.currentUser) {
    langPopup.style.display = 'block';
  } else {
    langPopup.style.display = 'none';
    updateLanguageUI();
    renderPosts();
    renderUsers();
    renderMessages();
  }
  showSection('feed');
</script>

</body>
</html>
