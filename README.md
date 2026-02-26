<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MusicMind · влияние музыки на человека</title>
  <!-- Font Awesome для иконок -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    /* ОБЩИЕ СТИЛИ */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Roboto, system-ui, sans-serif;
    }

    body {
      background-color: #f8faff;
      color: #1e2b3c;
      line-height: 1.5;
      scroll-behavior: smooth;
    }

    /* НАВИГАЦИЯ */
    .navbar {
      background: white;
      padding: 0.8rem 2rem;
      box-shadow: 0 4px 12px rgba(0, 20, 40, 0.05);
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      position: sticky;
      top: 0;
      z-index: 10;
    }

    .logo {
      font-size: 1.8rem;
      font-weight: 600;
      color: #5f4b8b;
      letter-spacing: -0.5px;
    }

    .logo i {
      color: #7aa5c2;
      margin-right: 6px;
    }

    .nav-links {
      display: flex;
      gap: 1.8rem;
      flex-wrap: wrap;
    }

    .nav-links a {
      text-decoration: none;
      color: #2c3e50;
      font-weight: 500;
      transition: color 0.2s;
      font-size: 1.1rem;
    }

    .nav-links a:hover {
      color: #5f4b8b;
    }

    /* КОНТЕЙНЕР */
    .container {
      max-width: 1200px;
      margin: 2rem auto;
      padding: 0 2rem;
    }

    /* ЗАГОЛОВКИ */
    h1 {
      font-size: 2.8rem;
      font-weight: 600;
      color: #1e2b3c;
      line-height: 1.2;
    }

    h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
      color: #2c3e50;
      font-weight: 500;
      border-left: 6px solid #a28cc0;
      padding-left: 1rem;
    }

    h3 {
      font-size: 1.5rem;
      margin-bottom: 0.5rem;
      color: #3a4a5c;
    }

    .subtitle {
      font-size: 1.3rem;
      color: #4a5e71;
      margin: 1rem 0 2rem;
    }

    /* КАРТОЧКИ */
    .card-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 2rem;
      margin: 3rem 0;
    }

    .card {
      background: white;
      border-radius: 24px;
      padding: 1.8rem 1.5rem;
      box-shadow: 0 10px 25px -8px rgba(95, 75, 139, 0.15);
      transition: transform 0.2s, box-shadow 0.2s;
      cursor: pointer;
      border: 1px solid rgba(255,255,255,0.5);
      display: flex;
      flex-direction: column;
    }

    .card:hover {
      transform: translateY(-6px);
      box-shadow: 0 20px 30px -10px rgba(122, 165, 194, 0.3);
    }

    .card i {
      font-size: 2.5rem;
      color: #7aa5c2;
      margin-bottom: 1rem;
    }

    .card h3 {
      margin-bottom: 0.8rem;
      font-weight: 600;
    }

    .card p {
      color: #3f5568;
      flex: 1;
    }

    /* СЕКЦИИ */
    .section {
      background: white;
      border-radius: 32px;
      padding: 2.5rem;
      margin: 3rem 0;
      box-shadow: 0 12px 30px rgba(0,0,0,0.03);
      border: 1px solid #e9ecf5;
    }

    /* КНОПКИ */
    .btn {
      display: inline-block;
      background: #7aa5c2;
      color: white;
      padding: 0.9rem 2rem;
      border-radius: 40px;
      text-decoration: none;
      font-weight: 600;
      font-size: 1.1rem;
      border: none;
      cursor: pointer;
      transition: background 0.2s;
      box-shadow: 0 8px 14px -6px #7aa5c2;
    }

    .btn:hover {
      background: #5f4b8b;
      box-shadow: 0 8px 14px -6px #5f4b8b;
    }

    .btn-small {
      background: #e0e9f5;
      color: #1e2b3c;
      padding: 0.6rem 1.5rem;
      border-radius: 40px;
      font-weight: 500;
      border: none;
      cursor: pointer;
      transition: all 0.2s;
    }

    .btn-small:hover {
      background: #cbdaea;
    }

    /* MUSIC FINDER */
    .selector-panel {
      background: #f1f6fd;
      border-radius: 28px;
      padding: 2rem;
      margin: 2rem 0;
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      align-items: flex-end;
    }

    .selector-group {
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
      min-width: 180px;
    }

    .selector-group label {
      font-weight: 600;
      color: #4a5e71;
    }

    .selector-group select {
      padding: 0.8rem 1rem;
      border-radius: 40px;
      border: 1px solid #ccdaea;
      background: white;
      font-size: 1rem;
      outline: none;
    }

    .genre-suggest {
      background: white;
      border-radius: 40px;
      padding: 1.5rem 2rem;
      margin-top: 1.5rem;
      font-size: 1.2rem;
      font-weight: 500;
      border: 1px solid #dbe2ed;
    }

    /* ЭКСПЕРИМЕНТ */
    .track-card {
      background: #f1f6fd;
      border-radius: 28px;
      padding: 2rem;
      margin: 2rem 0;
    }

    .track-name {
      font-size: 1.8rem;
      font-weight: 600;
      color: #1e2b3c;
      margin-bottom: 1rem;
    }

    .rating-group {
      margin: 1.5rem 0;
    }

    .rating-group p {
      font-weight: 600;
      margin-bottom: 0.5rem;
    }

    .scale {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .scale label {
      display: flex;
      align-items: center;
      gap: 0.3rem;
      background: white;
      padding: 0.5rem 1.2rem;
      border-radius: 40px;
      border: 1px solid #ccdaea;
    }

    .like-group {
      display: flex;
      gap: 1.5rem;
      margin: 1.5rem 0;
    }

    .like-group label {
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }

    .experiment-message {
      background: #e5d9f2;
      border-radius: 40px;
      padding: 1rem 2rem;
      margin-top: 1.5rem;
      font-style: italic;
    }

    /* КУЛЬТУРА */
    .culture-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2rem;
      margin-top: 2rem;
    }

    .culture-card {
      background: #f1f6fd;
      border-radius: 28px;
      padding: 1.8rem;
    }

    .culture-card h4 {
      font-size: 1.4rem;
      margin-bottom: 1rem;
      color: #2c3e50;
    }

    .culture-list {
      list-style: none;
    }

    .culture-list li {
      margin: 0.8rem 0;
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }

    .culture-list i {
      color: #7aa5c2;
      width: 1.6rem;
    }

    /* ФУТЕР */
    .footer {
      text-align: center;
      padding: 2rem;
      color: #5f7184;
      border-top: 1px solid #dbe2ed;
      margin-top: 3rem;
    }

    /* АДАПТАЦИЯ */
    @media (max-width: 700px) {
      .navbar {
        flex-direction: column;
        gap: 0.8rem;
      }
      .nav-links {
        gap: 1rem;
        justify-content: center;
      }
      h1 { font-size: 2.2rem; }
      .culture-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<!-- НАВИГАЦИЯ -->
<nav class="navbar">
  <div class="logo">
    <i class="fas fa-headphones-alt"></i> MusicMind
  </div>
  <div class="nav-links">
    <a href="#home">Home</a>
    <a href="#about">About Music</a>
    <a href="#finder">Music Finder</a>
    <a href="#experiment">Experiment</a>
    <a href="#culture">Music & Culture</a>
  </div>
</nav>

<main class="container">

  <!-- ГЛАВНАЯ -->
  <section id="home">
    <h1>The Influence of Music on Human Life</h1>
    <p class="subtitle">Explore how music affects your mood, focus, and daily life.</p>
    <a href="#card-section" class="btn"><i class="fas fa-play"></i> Start Exploring</a>
  </section>

  <!-- КАРТОЧКИ -->
  <div id="card-section" class="card-grid">
    <div class="card" onclick="location.href='#about'">
      <i class="fas fa-music"></i>
      <h3>Power of Music</h3>
      <p>How music shapes emotions, focus, and relaxation. Discover why it matters.</p>
    </div>
    <div class="card" onclick="location.href='#finder'">
      <i class="fas fa-sliders-h"></i>
      <h3>Mood & Activity Matcher</h3>
      <p>Find the perfect genre for your mood and activity.</p>
    </div>
    <div class="card" onclick="location.href='#experiment'">
      <i class="fas fa-flask"></i>
      <h3>Music Experiment</h3>
      <p>Test how different tracks change your feelings.</p>
    </div>
    <div class="card" onclick="location.href='#culture'">
      <i class="fas fa-globe-americas"></i>
      <h3>Music in Culture & Life</h3>
      <p>Explore music across the world and in movies, games, sports.</p>
    </div>
  </div>

  <!-- ABOUT MUSIC -->
  <section id="about" class="section">
    <h2><i class="fas fa-star" style="color:#7aa5c2; margin-right:10px;"></i> Power of Music</h2>
    <p style="font-size:1.2rem; margin-bottom:2rem;">Learn how music affects emotions, focus, and daily life.</p>
    
    <div style="display:grid; grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); gap:1.5rem;">
      <div style="background:#f1f6fd; border-radius:28px; padding:1.5rem;">
        <i class="fas fa-smile" style="font-size:2rem; color:#5f4b8b;"></i>
        <h4 style="margin:0.7rem 0;">Music & Mood</h4>
        <p>Happy songs boost serotonin; calm music reduces anxiety. Music changes brain chemicals like dopamine and serotonin (Sazandrishvili, 2024).</p>
      </div>
      <div style="background:#f1f6fd; border-radius:28px; padding:1.5rem;">
        <i class="fas fa-brain" style="font-size:2rem; color:#7aa5c2;"></i>
        <h4 style="margin:0.7rem 0;">Music & Focus</h4>
        <p>Instrumental or lo-fi helps concentration by blocking distractions. Studies show music affects cognitive performance differently based on task type (Wang, 2023).</p>
      </div>
      <div style="background:#f1f6fd; border-radius:28px; padding:1.5rem;">
        <i class="fas fa-bed" style="font-size:2rem; color:#5f4b8b;"></i>
        <h4 style="margin:0.7rem 0;">Music & Relaxation</h4>
        <p>Slow tempos lower heart rate and stress. Music therapy reduces stress and develops self-confidence (Deshmukh and Gupta, 2022).</p>
      </div>
      <div style="background:#f1f6fd; border-radius:28px; padding:1.5rem;">
        <i class="fas fa-heart" style="font-size:2rem; color:#7aa5c2;"></i>
        <h4 style="margin:0.7rem 0;">Why Music Matters</h4>
        <p>It connects us, tells stories, and helps express feelings. Music alters brain chemicals and improves emotional balance (Piccardi and Palmiero, 2024).</p>
      </div>
    </div>
  </section>

  <!-- MUSIC FINDER -->
  <section id="finder" class="section">
    <h2><i class="fas fa-magic" style="color:#7aa5c2; margin-right:10px;"></i> Mood & Activity Matcher</h2>
    <p class="subtitle" style="margin-top:-0.5rem;">Select your mood and activity – we'll suggest music genres.</p>

    <div class="selector-panel">
      <div class="selector-group">
        <label for="moodSelect"><i class="far fa-smile"></i> Mood</label>
        <select id="moodSelect">
          <option value="happy">Happy</option>
          <option value="calm">Calm</option>
          <option value="sad">Sad</option>
          <option value="energetic">Energetic</option>
        </select>
      </div>
      <div class="selector-group">
        <label for="activitySelect"><i class="fas fa-running"></i> Activity</label>
        <select id="activitySelect">
          <option value="studying">Studying</option>
          <option value="sports">Sports</option>
          <option value="relaxing">Relaxing</option>
          <option value="walking">Walking</option>
        </select>
      </div>
      <button class="btn-small" id="suggestBtn"><i class="fas fa-search"></i> Suggest genres</button>
    </div>

    <div id="suggestionBox" class="genre-suggest">
      <i class="fas fa-headphones" style="margin-right:10px;"></i>
      <span id="genreResult">Select mood & activity to see suggestions</span>
    </div>

    <p style="margin-top:1.5rem; color:#4a5e71;"><i class="fas fa-lightbulb"></i> Based on research by Wang (2023) about how different music genres affect cognitive performance and emotions.</p>
  </section>

  <!-- EXPERIMENT -->
  <section id="experiment" class="section">
    <h2><i class="fas fa-flask" style="color:#7aa5c2;"></i> Music Experiment</h2>
    <p>Test how music affects your mood. Rate each track.</p>

    <div class="track-card" id="experimentTrackCard">
      <div class="track-name" id="currentTrackDisplay">🎵 "Sunny Day" (Happy Pop)</div>

      <div class="rating-group">
        <p>How does this music make you feel? (1 = very bad, 5 = very good)</p>
        <div class="scale" id="moodScale">
          <label><input type="radio" name="moodRating" value="1"> 1</label>
          <label><input type="radio" name="moodRating" value="2"> 2</label>
          <label><input type="radio" name="moodRating" value="3"> 3</label>
          <label><input type="radio" name="moodRating" value="4"> 4</label>
          <label><input type="radio" name="moodRating" value="5"> 5</label>
        </div>
      </div>

      <div class="rating-group">
        <p>Did you like it?</p>
        <div class="like-group" id="likeGroup">
          <label><input type="radio" name="likeTrack" value="yes"> Yes</label>
          <label><input type="radio" name="likeTrack" value="no"> No</label>
          <label><input type="radio" name="likeTrack" value="neutral"> Neutral</label>
        </div>
      </div>

      <button class="btn-small" id="nextTrackBtn"><i class="fas fa-forward"></i> Next track</button>

      <div id="experimentFeedback" class="experiment-message">
        ⚡ Rate the track and go to the next one. Inspired by the PANAS mood scale (Deshmukh and Gupta, 2022).
      </div>
    </div>
  </section>

  <!-- MUSIC & CULTURE -->
  <section id="culture" class="section">
    <h2><i class="fas fa-globe" style="color:#5f4b8b;"></i> Music in Culture and Life</h2>
    <p class="subtitle">Discover how music connects people and is used everywhere.</p>

    <div class="culture-grid">
      <div class="culture-card">
        <h4><i class="fas fa-earth-asia"></i> Music Worldwide</h4>
        <ul class="culture-list">
          <li><i class="fas fa-music"></i> European: Classical, folk, electronic</li>
          <li><i class="fas fa-music"></i> Asian: K-pop, Gamelan, Bollywood</li>
          <li><i class="fas fa-music"></i> African: Drumming, Afrobeat, Highlife</li>
          <li><i class="fas fa-music"></i> American: Jazz, Blues, Rock, Hip-hop</li>
        </ul>
        <p style="margin-top:1rem;">Music connects cultures and people across the world.</p>
      </div>

      <div class="culture-card">
        <h4><i class="fas fa-film"></i> Music in Life</h4>
        <ul class="culture-list">
          <li><i class="fas fa-film"></i> Movies: Scores set the emotion</li>
          <li><i class="fas fa-gamepad"></i> Games: Immersive soundtracks</li>
          <li><i class="fas fa-mask"></i> Theater: Musicals tell stories</li>
          <li><i class="fas fa-medal"></i> Sports: Pump-up anthems</li>
          <li><i class="fas fa-microphone-alt"></i> Concerts: Shared experience</li>
        </ul>
      </div>
    </div>
  </section>

  <footer class="footer">
    <p>MusicMind · MYP Personal Project · The influence of music on human life</p>
    <p>Based on research: Deshmukh and Gupta (2022), Wang (2023), Sazandrishvili (2024), Piccardi and Palmiero (2024)</p>
  </footer>
</main>

<script>
  (function() {
    // MUSIC FINDER
    const moodSelect = document.getElementById('moodSelect');
    const activitySelect = document.getElementById('activitySelect');
    const suggestBtn = document.getElementById('suggestBtn');
    const genreResult = document.getElementById('genreResult');

    const suggestions = {
      'happy+studying': ['Upbeat classical', 'Video game soundtracks', 'Indie pop'],
      'happy+sports': ['Dance pop', 'Electro', 'Rock'],
      'happy+relaxing': ['Sunny reggae', 'Bossa nova', 'Happy acoustic'],
      'happy+walking': ['Pop', 'Funk', 'Ska'],
      'calm+studying': ['Lo-fi', 'Classical piano', 'Ambient'],
      'calm+sports': ['Soft rock', 'Chillstep', 'Mid-tempo electronica'],
      'calm+relaxing': ['Nature sounds', 'Meditation music', 'Spa piano'],
      'calm+walking': ['Smooth jazz', 'Acoustic folk', 'Downtempo'],
      'sad+studying': ['Solo piano', 'Melancholic indie', 'Strings'],
      'sad+sports': ['Emo rock', 'Power ballads'],
      'sad+relaxing': ['Ambient', 'Sad core', 'Minimal piano'],
      'sad+walking': ['Mellow rock', 'Singer-songwriter', 'Blues'],
      'energetic+studying': ['High-focus electronic', 'Epic orchestral'],
      'energetic+sports': ['Drum & bass', 'Hard rock', 'Heavy metal'],
      'energetic+relaxing': ['World music', 'Latin rhythms'],
      'energetic+walking': ['Power pop', 'Marching band', 'Upbeat rock']
    };

    function getSuggestion(mood, activity) {
      const key = mood + '+' + activity;
      return suggestions[key] || ['Try different combination!'];
    }

    suggestBtn.addEventListener('click', () => {
      const mood = moodSelect.value;
      const activity = activitySelect.value;
      const genres = getSuggestion(mood, activity);
      genreResult.innerHTML = `<i class="fas fa-music"></i> ${genres.join(' · ')}`;
    });

    // EXPERIMENT
    const tracks = [
      { name: '🌞 "Sunny Day" (Happy Pop)' },
      { name: '🌧️ "Rainy Mood" (Ambient)' },
      { name: '⚡ "Ignite" (Electronic Rock)' },
      { name: '🎻 "Reflection" (Solo Cello)' },
      { name: '🌊 "Ocean Waves" (Nature)' }
    ];

    let trackIndex = 0;
    const trackDisplay = document.getElementById('currentTrackDisplay');
    const moodRadios = document.querySelectorAll('input[name="moodRating"]');
    const likeRadios = document.querySelectorAll('input[name="likeTrack"]');
    const feedbackDiv = document.getElementById('experimentFeedback');
    const nextBtn = document.getElementById('nextTrackBtn');

    function updateTrackDisplay() {
      trackDisplay.textContent = `🎵 ${tracks[trackIndex].name}`;
    }

    function clearRatings() {
      moodRadios.forEach(r => r.checked = false);
      likeRadios.forEach(r => r.checked = false);
    }

    nextBtn.addEventListener('click', () => {
      trackIndex = (trackIndex + 1) % tracks.length;
      updateTrackDisplay();
      clearRatings();
      feedbackDiv.innerHTML = '⏩ New track! Rate how it makes you feel.';
    });

    updateTrackDisplay();
    clearRatings();

    // Highlight active nav on scroll
    const sections = document.querySelectorAll('section');
    const navLinks = document.querySelectorAll('.nav-links a');

    window.addEventListener('scroll', () => {
      let current = '';
      sections.forEach(section => {
        const sectionTop = section.offsetTop - 80;
        const sectionHeight = section.clientHeight;
        if (pageYOffset >= sectionTop && pageYOffset < sectionTop + sectionHeight) {
          current = section.getAttribute('id');
        }
      });

      navLinks.forEach(link => {
        link.style.fontWeight = '500';
        link.style.color = '#2c3e50';
        if (link.getAttribute('href') === `#${current}`) {
          link.style.fontWeight = '700';
          link.style.color = '#5f4b8b';
        }
      });
    });
  })();
</script>
</body>
</html># MusicMind.
