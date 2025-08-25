# wd_dashobard_
music-player.html
@CodeAlpha&#CodeA
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Music Player App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #1e3c72, #2a5298);
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .player {
      background: #222;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.4);
      width: 320px;
      text-align: center;
    }
    .player h2 {
      margin-bottom: 10px;
    }
    .controls {
      margin: 20px 0;
    }
    button {
      background: #444;
      color: #fff;
      border: none;
      padding: 10px 15px;
      margin: 5px;
      border-radius: 8px;
      cursor: pointer;
      transition: 0.3s;
    }
    button:hover {
      background: #666;
    }
    input[type="range"] {
      width: 100%;
      margin: 15px 0;
    }
  </style>
</head>
<body>

<div class="player">
  <h2>🎶 Music Player</h2>
  <audio id="audio" src="song.mp3"></audio>
  
  <div class="controls">
    <button onclick="playAudio()">▶️ Play</button>
    <button onclick="pauseAudio()">⏸ Pause</button>
    <button onclick="stopAudio()">⏹ Stop</button>
  </div>
  
  <input type="range" id="seek" value="0" min="0" step="1"/>
</div>

<script>
  const audio = document.getElementById("audio");
  const seek = document.getElementById("seek");

  // Play
  function playAudio() {
    audio.play();
  }

  // Pause
  function pauseAudio() {
    audio.pause();
  }

  // Stop
  function stopAudio() {
    audio.pause();
    audio.currentTime = 0;
  }

  // Update seek bar
  audio.addEventListener("timeupdate", () => {
    seek.max = audio.duration;
    seek.value = audio.currentTime;
  });

  // Seek change
  seek.addEventListener("input", () => {
    audio.currentTime = seek.value;
  });
</script>

</body>
</html>

