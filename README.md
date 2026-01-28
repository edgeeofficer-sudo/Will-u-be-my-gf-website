<!doctype html>
<html lang="en" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Girlfriend?</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@400;500;600;700&amp;family=Quicksand:wght@300;400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    
    * {
      font-family: 'Quicksand', sans-serif;
    }
    
    .handwritten {
      font-family: 'Caveat', cursive;
    }
    
    @keyframes float {
      0%, 100% { transform: translateY(0) rotate(0deg); opacity: 0.7; }
      50% { transform: translateY(-20px) rotate(10deg); opacity: 1; }
    }
    
    @keyframes floatSlow {
      0%, 100% { transform: translateY(0) rotate(-5deg); opacity: 0.5; }
      50% { transform: translateY(-30px) rotate(5deg); opacity: 0.8; }
    }
    
    @keyframes pulse {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.05); }
    }
    
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      25% { transform: translateY(-8px); }
      50% { transform: translateY(0); }
      75% { transform: translateY(-4px); }
    }
    
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    
    @keyframes heartBeat {
      0% { transform: scale(1); }
      14% { transform: scale(1.3); }
      28% { transform: scale(1); }
      42% { transform: scale(1.3); }
      70% { transform: scale(1); }
    }
    
    @keyframes confetti {
      0% { transform: translateY(0) rotate(0deg); opacity: 1; }
      100% { transform: translateY(100%) rotate(720deg); opacity: 0; }
    }
    
    @keyframes sparkle {
      0%, 100% { opacity: 0; transform: scale(0); }
      50% { opacity: 1; transform: scale(1); }
    }
    
    @keyframes slideIn {
      from { opacity: 0; transform: scale(0.8); }
      to { opacity: 1; transform: scale(1); }
    }
    
    @keyframes rotate {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }
    
    .floating-heart {
      animation: float 4s ease-in-out infinite;
    }
    
    .floating-heart-slow {
      animation: floatSlow 6s ease-in-out infinite;
    }
    
    .pulse-animation {
      animation: pulse 2s ease-in-out infinite;
    }
    
    .bounce-animation {
      animation: bounce 1s ease-in-out infinite;
    }
    
    .fade-in-up {
      animation: fadeInUp 0.8s ease-out forwards;
    }
    
    .heart-beat {
      animation: heartBeat 1.5s ease-in-out infinite;
    }
    
    .yes-btn {
      transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    }
    
    .yes-btn:hover {
      transform: scale(1.1);
      box-shadow: 0 20px 40px rgba(236, 72, 153, 0.4);
    }
    
    .no-btn {
      transition: all 0.2s ease;
      position: absolute;
    }
    
    .confetti-piece {
      position: fixed;
      width: 10px;
      height: 10px;
      animation: confetti 3s ease-out forwards;
      pointer-events: none;
      z-index: 100;
    }
    
    .success-overlay {
      animation: slideIn 0.5s ease-out forwards;
    }
    
    .sparkle {
      position: absolute;
      animation: sparkle 1.5s ease-in-out infinite;
    }
    
    .gradient-bg {
      background: linear-gradient(135deg, #fce7f3 0%, #e9d5ff 50%, #fef3c7 100%);
    }
    
    .card-shadow {
      box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.1), 0 0 0 1px rgba(255, 255, 255, 0.5) inset;
    }
    
    .reject-message {
      animation: fadeInUp 0.5s ease-out forwards;
    }
    
    .music-toggle {
      position: fixed;
      bottom: 20px;
      right: 20px;
      z-index: 50;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    .music-toggle:hover {
      transform: scale(1.1);
    }
    
    .music-toggle.playing .music-icon {
      animation: rotate 4s linear infinite;
    }
    
    .music-icon {
      transition: transform 0.3s ease;
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full gradient-bg overflow-auto">
  <div id="app-container" class="min-h-full w-full relative overflow-hidden"><!-- Floating Hearts Background -->
   <div id="floating-hearts" class="absolute inset-0 pointer-events-none overflow-hidden">
    <div class="floating-heart absolute text-4xl" style="left: 10%; top: 20%; animation-delay: 0s;">
     💕
    </div>
    <div class="floating-heart-slow absolute text-3xl" style="left: 80%; top: 15%; animation-delay: 1s;">
     💗
    </div>
    <div class="floating-heart absolute text-2xl" style="left: 25%; top: 70%; animation-delay: 2s;">
     💖
    </div>
    <div class="floating-heart-slow absolute text-4xl" style="left: 70%; top: 60%; animation-delay: 0.5s;">
     💝
    </div>
    <div class="floating-heart absolute text-3xl" style="left: 5%; top: 50%; animation-delay: 1.5s;">
     💓
    </div>
    <div class="floating-heart-slow absolute text-2xl" style="left: 90%; top: 40%; animation-delay: 2.5s;">
     💞
    </div>
    <div class="floating-heart absolute text-3xl" style="left: 50%; top: 10%; animation-delay: 3s;">
     💘
    </div>
    <div class="floating-heart-slow absolute text-4xl" style="left: 35%; top: 85%; animation-delay: 0.8s;">
     💕
    </div>
    <div class="floating-heart absolute text-2xl" style="left: 60%; top: 80%; animation-delay: 1.8s;">
     💗
    </div>
    <div class="floating-heart-slow absolute text-3xl" style="left: 15%; top: 90%; animation-delay: 2.8s;">
     💖
    </div>
   </div><!-- Music Toggle Button -->
   <div id="music-toggle" class="music-toggle">
    <div class="bg-white/80 backdrop-blur-md rounded-full p-4 shadow-lg">
     <div class="music-icon text-3xl">
      🎵
     </div>
    </div>
    <div id="music-status" class="text-xs text-center mt-1 text-purple-600 font-semibold">
     Click for music
    </div>
   </div><!-- Hidden audio element -->
   <audio id="background-music" loop><source src="data:audio/mpeg;base64,SUQzBAAAAAAAI1RTU0UAAAAPAAADTGF2ZjU4Ljc2LjEwMAAAAAAAAAAAAAAA//tQAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAWGluZwAAAA8AAAACAAADhAC7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7u7v////////////////////////////////////////////////////////////////AAAAATGF2YzU4LjEzAAAAAAAAAAAAAAAAJAAAAAAAAAAAA4SZL8ZUAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA//sQZAAP8AAAaQAAAAgAAA0gAAABAAABpAAAACAAADSAAAAETEFNRTMuMTAwVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVVQ==" type="audio/mpeg">
   </audio><!-- Main Content -->
   <div id="main-content" class="relative z-10 min-h-full flex flex-col items-center justify-center px-4 py-8"><!-- Hero Card -->
    <div class="bg-white/70 backdrop-blur-lg rounded-3xl card-shadow p-8 md:p-12 max-w-lg w-full text-center fade-in-up"><!-- Decorative Hearts -->
     <div class="flex justify-center mb-4"><span class="text-5xl heart-beat">💝</span>
     </div><!-- Main Question -->
     <h1 id="main-question" class="handwritten text-4xl md:text-6xl font-bold text-pink-600 mb-4 leading-tight">Will You Be My Girlfriend?</h1><!-- Subtext -->
     <p id="subtext" class="text-lg md:text-xl text-purple-600/80 mb-8 font-medium">I've been meaning to ask you something special…</p><!-- Sparkles around text -->
     <div class="relative"><span class="sparkle text-yellow-400 text-xl" style="top: -20px; left: 10%; animation-delay: 0s;">✨</span> <span class="sparkle text-pink-400 text-xl" style="top: -10px; right: 15%; animation-delay: 0.5s;">✨</span> <span class="sparkle text-purple-400 text-xl" style="bottom: -20px; left: 20%; animation-delay: 1s;">✨</span>
     </div><!-- Buttons Container -->
     <div id="buttons-container" class="relative h-32 flex items-center justify-center gap-6"><!-- YES Button --> <button id="yes-btn" class="yes-btn bounce-animation bg-gradient-to-r from-pink-500 to-rose-500 text-white font-bold text-xl md:text-2xl px-10 py-4 rounded-full shadow-lg hover:from-pink-600 hover:to-rose-600 focus:outline-none focus:ring-4 focus:ring-pink-300"> 💖 YES </button> <!-- NO Button --> <button id="no-btn" class="no-btn bg-gradient-to-r from-gray-400 to-gray-500 text-white font-bold text-xl md:text-2xl px-10 py-4 rounded-full shadow-lg hover:from-gray-500 hover:to-gray-600 focus:outline-none focus:ring-4 focus:ring-gray-300" style="position: relative;"> 💔 NO </button>
     </div><!-- Reject Message (hidden initially) -->
     <div id="reject-message" class="hidden mt-4">
      <p class="reject-message text-purple-600 font-medium text-lg">Eh kok nolak 😔 coba klik lagi…</p>
     </div>
    </div><!-- Love Quote -->
    <p id="footer-text" class="mt-8 text-purple-500/60 text-sm md:text-base font-medium fade-in-up" style="animation-delay: 0.5s;">Made with 💕 just for you</p>
   </div><!-- Success Overlay (hidden initially) -->
   <div id="success-overlay" class="hidden fixed inset-0 z-50 flex items-center justify-center gradient-bg">
    <div class="success-overlay bg-white/80 backdrop-blur-xl rounded-3xl card-shadow p-8 md:p-16 max-w-2xl w-full mx-4 text-center">
     <div class="text-8xl mb-6 heart-beat">
      💗
     </div>
     <h2 id="success-message" class="handwritten text-4xl md:text-6xl font-bold text-pink-600 mb-6">YAY!! I'm so happy 💗 Thank you for being mine!</h2>
     <div class="flex justify-center gap-4 text-4xl"><span class="floating-heart">💕</span> <span class="floating-heart-slow">💖</span> <span class="floating-heart">💝</span> <span class="floating-heart-slow">💗</span> <span class="floating-heart">💞</span>
     </div>
     <p id="success-subtext" class="mt-8 text-purple-500 text-lg font-medium">You just made me the happiest person in the world! 🥰</p>
    </div>
   </div>
  </div>
  <script>
    // Default configuration
    const defaultConfig = {
      main_question: "Will You Be My Girlfriend?",
      subtext: "I've been meaning to ask you something special…",
      yes_button_text: "💖 YES",
      no_button_text: "💔 NO",
      success_message: "YAY!! I'm so happy 💗 Thank you for being mine!",
      reject_message: "Eh kok nolak 😔 coba klik lagi…",
      footer_text: "Made with 💕 just for you",
      success_subtext: "You just made me the happiest person in the world! 🥰",
      background_color: "#fce7f3",
      primary_color: "#ec4899",
      secondary_color: "#a855f7",
      text_color: "#db2777",
      accent_color: "#f472b6",
      font_family: "Quicksand",
      font_size: 16
    };
    
    let config = { ...defaultConfig };
    
    // Music functionality
    const musicToggle = document.getElementById('music-toggle');
    const backgroundMusic = document.getElementById('background-music');
    const musicStatus = document.getElementById('music-status');
    let isPlaying = false;
    
    musicToggle.addEventListener('click', () => {
      if (isPlaying) {
        backgroundMusic.pause();
        musicToggle.classList.remove('playing');
        musicStatus.textContent = 'Music off';
        isPlaying = false;
      } else {
        backgroundMusic.play().catch(err => {
          console.log('Audio playback prevented:', err);
          musicStatus.textContent = 'Music unavailable';
        });
        musicToggle.classList.add('playing');
        musicStatus.textContent = 'Music on 🎶';
        isPlaying = true;
      }
    });
    
    // NO button escape logic
    const noBtn = document.getElementById('no-btn');
    const buttonsContainer = document.getElementById('buttons-container');
    const rejectMessage = document.getElementById('reject-message');
    let escapeCount = 0;
    
    function getRandomPosition() {
      const container = buttonsContainer.getBoundingClientRect();
      const btnWidth = noBtn.offsetWidth;
      const btnHeight = noBtn.offsetHeight;
      
      const maxX = container.width - btnWidth - 20;
      const maxY = container.height - btnHeight;
      
      const randomX = Math.random() * maxX - maxX / 2;
      const randomY = Math.random() * maxY - maxY / 2;
      
      return { x: randomX, y: randomY };
    }
    
    function escapeButton() {
      const pos = getRandomPosition();
      noBtn.style.transform = `translate(${pos.x}px, ${pos.y}px)`;
      escapeCount++;
      
      if (escapeCount >= 2) {
        rejectMessage.classList.remove('hidden');
        const rejectText = document.querySelector('#reject-message p');
        rejectText.textContent = config.reject_message || defaultConfig.reject_message;
      }
    }
    
    noBtn.addEventListener('mouseenter', escapeButton);
    noBtn.addEventListener('touchstart', (e) => {
      e.preventDefault();
      escapeButton();
    });
    
    // YES button click - show success
    const yesBtn = document.getElementById('yes-btn');
    const successOverlay = document.getElementById('success-overlay');
    const mainContent = document.getElementById('main-content');
    
    function createConfetti() {
      const colors = ['#ec4899', '#f472b6', '#a855f7', '#c084fc', '#fbbf24', '#fb7185', '#f9a8d4'];
      const shapes = ['❤️', '💕', '💖', '💗', '💝', '✨', '🌸', '🎀'];
      
      for (let i = 0; i < 50; i++) {
        const confetti = document.createElement('div');
        confetti.className = 'confetti-piece';
        confetti.style.left = Math.random() * 100 + '%';
        confetti.style.top = '-20px';
        confetti.style.animationDelay = Math.random() * 2 + 's';
        confetti.style.animationDuration = (Math.random() * 2 + 2) + 's';
        
        if (Math.random() > 0.5) {
          confetti.textContent = shapes[Math.floor(Math.random() * shapes.length)];
          confetti.style.fontSize = (Math.random() * 20 + 15) + 'px';
        } else {
          confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
          confetti.style.borderRadius = Math.random() > 0.5 ? '50%' : '2px';
          confetti.style.width = (Math.random() * 10 + 5) + 'px';
          confetti.style.height = (Math.random() * 10 + 5) + 'px';
        }
        
        document.body.appendChild(confetti);
        
        setTimeout(() => {
          confetti.remove();
        }, 5000);
      }
    }
    
    function showSuccess() {
      createConfetti();
      setTimeout(() => createConfetti(), 500);
      setTimeout(() => createConfetti(), 1000);
      
      successOverlay.classList.remove('hidden');
      mainContent.style.display = 'none';
    }
    
    yesBtn.addEventListener('click', showSuccess);
    
    // Element SDK Integration
    async function onConfigChange(newConfig) {
      config = { ...defaultConfig, ...newConfig };
      
      const baseSize = config.font_size || defaultConfig.font_size;
      const customFont = config.font_family || defaultConfig.font_family;
      const baseFontStack = 'Quicksand, sans-serif';
      const handwrittenStack = 'Caveat, cursive';
      
      // Update main question
      const questionEl = document.getElementById('main-question');
      if (questionEl) {
        questionEl.textContent = config.main_question || defaultConfig.main_question;
        questionEl.style.color = config.text_color || defaultConfig.text_color;
        questionEl.style.fontFamily = `${customFont}, ${handwrittenStack}`;
        questionEl.style.fontSize = `${baseSize * 2.5}px`;
      }
      
      // Update subtext
      const subtextEl = document.getElementById('subtext');
      if (subtextEl) {
        subtextEl.textContent = config.subtext || defaultConfig.subtext;
        subtextEl.style.color = config.secondary_color || defaultConfig.secondary_color;
        subtextEl.style.fontFamily = `${customFont}, ${baseFontStack}`;
        subtextEl.style.fontSize = `${baseSize * 1.1}px`;
      }
      
      // Update YES button
      const yesBtnEl = document.getElementById('yes-btn');
      if (yesBtnEl) {
        yesBtnEl.textContent = config.yes_button_text || defaultConfig.yes_button_text;
        yesBtnEl.style.background = `linear-gradient(to right, ${config.primary_color || defaultConfig.primary_color}, ${config.accent_color || defaultConfig.accent_color})`;
        yesBtnEl.style.fontFamily = `${customFont}, ${baseFontStack}`;
        yesBtnEl.style.fontSize = `${baseSize * 1.25}px`;
      }
      
      // Update NO button
      const noBtnEl = document.getElementById('no-btn');
      if (noBtnEl) {
        noBtnEl.textContent = config.no_button_text || defaultConfig.no_button_text;
        noBtnEl.style.fontFamily = `${customFont}, ${baseFontStack}`;
        noBtnEl.style.fontSize = `${baseSize * 1.25}px`;
      }
      
      // Update success message
      const successMsgEl = document.getElementById('success-message');
      if (successMsgEl) {
        successMsgEl.textContent = config.success_message || defaultConfig.success_message;
        successMsgEl.style.color = config.text_color || defaultConfig.text_color;
        successMsgEl.style.fontFamily = `${customFont}, ${handwrittenStack}`;
        successMsgEl.style.fontSize = `${baseSize * 2.5}px`;
      }
      
      // Update success subtext
      const successSubtextEl = document.getElementById('success-subtext');
      if (successSubtextEl) {
        successSubtextEl.textContent = config.success_subtext || defaultConfig.success_subtext;
        successSubtextEl.style.color = config.secondary_color || defaultConfig.secondary_color;
        successSubtextEl.style.fontFamily = `${customFont}, ${baseFontStack}`;
        successSubtextEl.style.fontSize = `${baseSize * 1.1}px`;
      }
      
      // Update reject message
      const rejectMsgEl = document.querySelector('#reject-message p');
      if (rejectMsgEl) {
        rejectMsgEl.textContent = config.reject_message || defaultConfig.reject_message;
        rejectMsgEl.style.color = config.secondary_color || defaultConfig.secondary_color;
        rejectMsgEl.style.fontFamily = `${customFont}, ${baseFontStack}`;
        rejectMsgEl.style.fontSize = `${baseSize * 1.1}px`;
      }
      
      // Update footer text
      const footerTextEl = document.getElementById('footer-text');
      if (footerTextEl) {
        footerTextEl.textContent = config.footer_text || defaultConfig.footer_text;
        footerTextEl.style.color = config.secondary_color || defaultConfig.secondary_color;
        footerTextEl.style.fontFamily = `${customFont}, ${baseFontStack}`;
        footerTextEl.style.fontSize = `${baseSize * 0.9}px`;
      }
      
      // Update background
      const appContainer = document.getElementById('app-container');
      if (appContainer) {
        appContainer.style.background = `linear-gradient(135deg, ${config.background_color || defaultConfig.background_color} 0%, #e9d5ff 50%, #fef3c7 100%)`;
      }
      
      const successBg = document.getElementById('success-overlay');
      if (successBg) {
        successBg.style.background = `linear-gradient(135deg, ${config.background_color || defaultConfig.background_color} 0%, #e9d5ff 50%, #fef3c7 100%)`;
      }
    }
    
    function mapToCapabilities(cfg) {
      return {
        recolorables: [
          {
            get: () => cfg.background_color || defaultConfig.background_color,
            set: (value) => {
              cfg.background_color = value;
              if (window.elementSdk) window.elementSdk.setConfig({ background_color: value });
            }
          },
          {
            get: () => cfg.primary_color || defaultConfig.primary_color,
            set: (value) => {
              cfg.primary_color = value;
              if (window.elementSdk) window.elementSdk.setConfig({ primary_color: value });
            }
          },
          {
            get: () => cfg.text_color || defaultConfig.text_color,
            set: (value) => {
              cfg.text_color = value;
              if (window.elementSdk) window.elementSdk.setConfig({ text_color: value });
            }
          },
          {
            get: () => cfg.secondary_color || defaultConfig.secondary_color,
            set: (value) => {
              cfg.secondary_color = value;
              if (window.elementSdk) window.elementSdk.setConfig({ secondary_color: value });
            }
          },
          {
            get: () => cfg.accent_color || defaultConfig.accent_color,
            set: (value) => {
              cfg.accent_color = value;
              if (window.elementSdk) window.elementSdk.setConfig({ accent_color: value });
            }
          }
        ],
        borderables: [],
        fontEditable: {
          get: () => cfg.font_family || defaultConfig.font_family,
          set: (value) => {
            cfg.font_family = value;
            if (window.elementSdk) window.elementSdk.setConfig({ font_family: value });
          }
        },
        fontSizeable: {
          get: () => cfg.font_size || defaultConfig.font_size,
          set: (value) => {
            cfg.font_size = value;
            if (window.elementSdk) window.elementSdk.setConfig({ font_size: value });
          }
        }
      };
    }
    
    function mapToEditPanelValues(cfg) {
      return new Map([
        ["main_question", cfg.main_question || defaultConfig.main_question],
        ["subtext", cfg.subtext || defaultConfig.subtext],
        ["yes_button_text", cfg.yes_button_text || defaultConfig.yes_button_text],
        ["no_button_text", cfg.no_button_text || defaultConfig.no_button_text],
        ["success_message", cfg.success_message || defaultConfig.success_message],
        ["reject_message", cfg.reject_message || defaultConfig.reject_message],
        ["footer_text", cfg.footer_text || defaultConfig.footer_text],
        ["success_subtext", cfg.success_subtext || defaultConfig.success_subtext]
      ]);
    }
    
    // Initialize SDK
    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities,
        mapToEditPanelValues
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9c5236f7c3ee7e08',t:'MTc2OTYyMTM5NS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>