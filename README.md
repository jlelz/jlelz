<!-- https://music.youtube.com/watch?v=U0MrkZiM6w8 -->

<style>
body {
  background: #000;
  overflow: hidden;
  margin: 0;
  height: 100vh;
}

.matrix-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  z-index: 2; /* Ensure it stays above the rain effect */
}

.matrix-text {
  color: #0f0;
  font-size: 80px;
  font-family: monospace;
  position: relative;
  text-shadow: 0 0 10px #0f0, 0 0 20px #0f0, 0 0 30px #0f0;
  z-index: 2; /* Ensure it stays above the rain effect */
}

.matrix-text::before {
  content: attr(data-text);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  animation: glitch 2s infinite;
  clip-path: polygon(0 0, 100% 0, 100% 45%, 0 45%);
  transform: translate(-2px, -2px);
  color: #0f0;
  text-shadow: 0 0 5px #0f0, 0 0 15px #0f0;
}

.rain {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: repeating-linear-gradient(
    0deg,
    rgba(0, 255, 0, 0.1) 0,
    rgba(0, 255, 0, 0.2) 2px,
    transparent 4px
  );
  animation: rain 10s linear infinite;
  z-index: 1; /* Place it behind the text */
}

/* Animation for the rain effect */
@keyframes rain {
  0% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(100%);
  }
}

/* Glitch effect for the text */
@keyframes glitch {
  0%, 100% {
    clip-path: polygon(0 0, 100% 0, 100% 45%, 0 45%);
    transform: translate(0);
  }
  33% {
    clip-path: polygon(0 0, 100% 0, 100% 15%, 0 15%);
    transform: translate(-5px, -5px);
  }
  66% {
    clip-path: polygon(0 85%, 100% 85%, 100% 100%, 0 100%);
    transform: translate(5px, 5px);
  }
}
</style>
<body class="matrix-bg">
  <div class="matrix-container">
    <h1 class="matrix-text" data-text="MATRIX">e̸̯̥͝v̵̰͚̦͛̊á̶̠́ș̸̀i̶̯͆͌̌v̵̼̬̠͐̊é̵̲̩̈͐͜ ̵̢̹͕̿̏a̷͎̖͚̍͗̂f̷͔͐</h1>
    <div class="rain"></div>
  </div>
</body>
