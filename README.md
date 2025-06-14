//Code for login page 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>KidSmart - Sign In</title>
  <style>
    /* Keep the same styles as before or copy from signup */
    body {
      font-family: 'Comic Sans MS', cursive;
      background: linear-gradient(135deg, #ffd54f, #f48fb1);
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }

    .container {
      background: #fffde7;
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      width: 90%;
      max-width: 400px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.2);
    }

    input {
      width: 90%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 10px;
      border: 2px solid #f48fb1;
    }

    button {
      background: #ffca28;
      padding: 10px 20px;
      border: none;
      border-radius: 15px;
      font-weight: bold;
      cursor: pointer;
    }

    .error {
      color: red;
      display: none;
      margin-top: 10px;
    }
  </style>
</head>
<body>

<div class="container">
  <h2>Sign In</h2>
  <input type="text" id="signinUser" placeholder="Username" required>
  <input type="password" id="signinPass" placeholder="Password" required>
  <button onclick="signIn()">Login 🚀</button>
  <div class="error" id="signinError">Invalid credentials!</div>
</div>

<script>
  function signIn() {
    const savedUser = localStorage.getItem("kidUser");
    const savedPass = localStorage.getItem("kidPass");

    const user = document.getElementById("signinUser").value;
    const pass = document.getElementById("signinPass").value;

    if (user === savedUser && pass === savedPass) {
      // Success
      window.location.href = "welcome.html";
    } else {
      document.getElementById("signinError").style.display = "block";
    }
  }
</script>

</body>
</html>







// Code for welcome page 

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Welcome to SmartKids!</title>
  <style>
    body {
      margin: 0;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: linear-gradient(to bottom right, #ffeb3b, #ff80ab);
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      color: #333;
      position: relative;
    }

    h1 {
      font-size: 3rem;
      margin-bottom: 10px;
      animation: popIn 1s ease-out forwards;
    }

    p {
      font-size: 1.3rem;
      animation: fadeIn 1.5s ease-out forwards;
    }

    .start-btn {
      margin-top: 20px;
      padding: 15px 30px;
      font-size: 1.2rem;
      border: none;
      border-radius: 25px;
      background-color: #ff4081;
      color: white;
      cursor: pointer;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      transition: transform 0.3s ease;
      animation: bounceIn 2s ease-in-out;
    }

    .start-btn:hover {
      transform: scale(1.1);
    }

    .shape {
      position: absolute;
      border-radius: 50%;
      opacity: 0.4;
      animation: float 6s infinite ease-in-out alternate;
    }

    .shape1 {
      width: 120px;
      height: 120px;
      background: #ff5722;
      top: 10%;
      left: 5%;
      animation-delay: 0s;
    }

    .shape2 {
      width: 100px;
      height: 100px;
      background: #4caf50;
      bottom: 15%;
      right: 10%;
      animation-delay: 1s;
    }

    .shape3 {
      width: 60px;
      height: 60px;
      background: #2196f3;
      top: 20%;
      right: 20%;
      animation-delay: 2s;
    }

    @keyframes float {
      from {
        transform: translateY(0px);
      }
      to {
        transform: translateY(20px);
      }
    }

    @keyframes popIn {
      0% { transform: scale(0.5); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes bounceIn {
      0% { transform: scale(0); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
  </style>
</head>
<body>

  <div class="shape shape1"></div>
  <div class="shape shape2"></div>
  <div class="shape shape3"></div>

  <h1>Welcome to SmartKids!</h1>
  <p>Let's have fun while learning important things 🎉</p>

  <button class="start-btn" onclick="startGame()">Start Playing</button>

  <script>
    function startGame() {
      window.location.href = "Children_Awareness.html"; // replace with your actual homepage
    }
  </script>
</body>
</html>






///code for page 1(3-5 age)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>SmartKids Puzzle Adventure - Ages 3-5 Multi-Games</title>
  <style>
    body {
      font-family: 'Comic Sans MS', sans-serif;
      background: #e0f7fa;
      margin: 0;
      padding: 20px;
      text-align: center;
    }
    h1 {
      color: #ff4081;
    }
    .game-buttons {
      margin-bottom: 30px;
    }
    .game-buttons button {
      margin: 5px;
      padding: 15px 25px;
      font-size: 1.2rem;
      border-radius: 15px;
      border: none;
      cursor: pointer;
      background-color: #fdd835;
      transition: background-color 0.3s, transform 0.3s;
    }
    .game-buttons button:hover,
    .game-buttons button.active {
      background-color: #ffeb3b;
      transform: scale(1.1);
    }
    .game-section {
      display: none;
      max-width: 600px;
      margin: 0 auto;
      background: #fff;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 0 10px #aaa;
      min-height: 300px;
    }
    .game-section.active {
      display: block;
    }

    /* Shared styles for games */
    .drop-zone {
      width: 100px;
      height: 100px;
      margin: 10px;
      display: inline-block;
      border: 3px dashed #aaa;
      border-radius: 20px;
    }
    .drop-zone.red { border-color: #e53935; }
    .drop-zone.blue { border-color: #1e88e5; }
    .drop-zone.yellow { border-color: #fdd835; }
    .drop-zone.circle { border-color: #8e24aa; }
    .drop-zone.square { border-color: #3949ab; }
    .drop-zone.triangle { border-color: #f4511e; }

    .draggable {
      width: 80px;
      height: 80px;
      margin: 10px;
      border-radius: 20px;
      cursor: grab;
      display: inline-block;
    }
    .draggable.red { background: #e53935; }
    .draggable.blue { background: #1e88e5; }
    .draggable.yellow { background: #fdd835; }
    .draggable.circle { background: #8e24aa; border-radius: 50%; }
    .draggable.square { background: #3949ab; border-radius: 10px; }
    .draggable.triangle {
      width: 0;
      height: 0;
      border-left: 40px solid transparent;
      border-right: 40px solid transparent;
      border-bottom: 80px solid #f4511e;
      background: none;
      border-radius: 0;
      margin: 20px;
      cursor: grab;
    }

    /*shape matching*/
    /* Drop Zones */
.drop-zone {
  display: inline-block;
  margin: 10px;
  position: relative;
}

.drop-zone.circle {
  width: 100px;
  height: 100px;
  border: 3px dashed #8e24aa;
  border-radius: 50%;
}

.drop-zone.square {
  width: 100px;
  height: 100px;
  border: 3px dashed #3949ab;
  border-radius: 10px;
}

    /* Counting Game */
    .counting-items {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin: 20px 0;
    }
    .counting-items div {
      width: 50px;
      height: 50px;
      background: #ffcc80;
      border-radius: 10px;
      font-size: 2rem;
      line-height: 50px;
      cursor: pointer;
      user-select: none;
    }
    #counting-result {
      margin-top: 20px;
      font-size: 1.2rem;
      color: #333;
      min-height: 40px;
    }

    /* Animal Sounds */
    #animal-sounds button {
      font-size: 3rem;
      margin: 10px;
      border: none;
      background: transparent;
      cursor: pointer;
    }

    /* Memory Game */
    .memory-grid {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      max-width: 300px;
      margin: 0 auto;
    }
    .memory-card {
      width: 70px;
      height: 70px;
      background: #81d4fa;
      border-radius: 15px;
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 2.5rem;
      user-select: none;
      color: transparent;
      transition: background-color 0.3s;
    }
    .memory-card.flipped,
    .memory-card.matched {
      color: black;
      background: #fff59d;
      cursor: default;
    }
  </style>
</head>
<body>
  <h1>SmartKids Puzzle Adventure - Ages 3-5</h1>

  <div class="game-buttons">
    <button class="active" data-game="color-matching">Color Matching</button>
    <button data-game="shape-matching">Shape Matching</button>
    <button data-game="counting">Counting</button>
    <button data-game="animal-sounds">Animal Sounds</button>
    <button data-game="memory-game">Memory Game</button>
  </div>

  <!-- Game Sections -->

  <!-- 1. Color Matching -->
  <section id="color-matching" class="game-section active">
    <p>Drag each colored shape onto the matching colored box.</p>
    <div>
      <div id="drop-red" class="drop-zone red" ondragover="allowDrop(event)" ondrop="drop(event)" data-color="red"></div>
      <div id="drop-blue" class="drop-zone blue" ondragover="allowDrop(event)" ondrop="drop(event)" data-color="blue"></div>
      <div id="drop-yellow" class="drop-zone yellow" ondragover="allowDrop(event)" ondrop="drop(event)" data-color="yellow"></div>
    </div>
    <div>
      <div id="drag-red" class="draggable red" draggable="true" ondragstart="drag(event)" data-color="red"></div>
      <div id="drag-blue" class="draggable blue" draggable="true" ondragstart="drag(event)" data-color="blue"></div>
      <div id="drag-yellow" class="draggable yellow" draggable="true" ondragstart="drag(event)" data-color="yellow"></div>
    </div>
    <div id="fact-color" style="margin-top: 20px; min-height: 40px;"></div>
  </section>

  
  <!-- 2. Shape Matching -->
  <section id="shape-matching" class="game-section">
    <p>Drag each shape onto its matching outline.</p>
    <div class="drop-container">
      <div id="drop-circle" class="drop-zone circle" ondragover="allowDrop(event)" ondrop="dropShape(event)" data-shape="circle"></div>
      <div id="drop-square" class="drop-zone square" ondragover="allowDrop(event)" ondrop="dropShape(event)" data-shape="square"></div>
      
    </div>
    <div class="drag-container">
      <div id="drag-circle" class="draggable circle" draggable="true" ondragstart="dragShape(event)" data-shape="circle"></div>
      <div id="drag-square" class="draggable square" draggable="true" ondragstart="dragShape(event)" data-shape="square"></div>
      
    </div>
    <div id="fact-shape" style="margin-top: 20px; min-height: 40px;"></div>
  </section>
  


  <!-- 3. Counting -->
  <section id="counting" class="game-section">
    <p>Click on the group of objects to count how many there are!</p>
    <div class="counting-items" id="counting-items">
      <div>🍎</div>
      <div>🍎</div>
      <div>🍎</div>
      <div>🍎</div>
      <div>🍎</div>
    </div>
    <button onclick="checkCount(5)">I counted 5</button>
    <div id="counting-result"></div>
  </section>

  <!-- 4. Animal Sounds -->
  <section id="animal-sounds" class="game-section">
    <p>Click a button to hear the animal sound and guess the animal!</p>
    <button onclick="playSound('dog')">🐶</button>
    <button onclick="playSound('cat')">🐱</button>
    <button onclick="playSound('cow')">🐄</button>
    <div id="animal-guess-result" style="margin-top: 20px; min-height: 40px;"></div>

    <audio id="dog-sound" src="https://actions.google.com/sounds/v1/animals/dog_barking.ogg"></audio>
    <audio id="cat-sound" src="https://actions.google.com/sounds/v1/animals/cat_meow.ogg"></audio>
    <audio id="cow-sound" src="https://actions.google.com/sounds/v1/animals/cow.ogg"></audio>
  </section>
  <!--section 5 memory game-->
  <section id="memory-game" class="game-section">
    <p>Click to flip and find all matching pairs!</p>
    <div class="memory-grid">
      <div class="memory-card" data-animal="🐶">🐶</div>
      <div class="memory-card" data-animal="🐱">🐱</div>
      <div class="memory-card" data-animal="🐶">🐶</div>
      <div class="memory-card" data-animal="🐱">🐱</div>
    </div>
    <div id="memory-result" style="margin-top: 20px; min-height: 40px;"></div>
  </section>

  <script>
    // --- Common: Show/Hide game sections ---
    const buttons = document.querySelectorAll('.game-buttons button');
    const sections = document.querySelectorAll('.game-section');
    buttons.forEach(btn => {
      btn.addEventListener('click', () => {
        buttons.forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
        const game = btn.getAttribute('data-game');
        sections.forEach(sec => {
          if (sec.id === game) sec.classList.add('active');
          else sec.classList.remove('active');
        });
      });
    });
  
    // --- Game 1: Color Matching ---
    let solvedColor = 0;
    function allowDrop(ev) {
      ev.preventDefault();
    }
    function drag(ev) {
      ev.dataTransfer.setData("color", ev.target.getAttribute('data-color'));
      ev.dataTransfer.setData("id", ev.target.id);
    }
    function drop(ev) {
      ev.preventDefault();
      const dropColor = ev.currentTarget.getAttribute('data-color');
      const dragColor = ev.dataTransfer.getData("color");
      const dragId = ev.dataTransfer.getData("id");
      if (dropColor === dragColor) {
        const draggedElem = document.getElementById(dragId);
        if (draggedElem.parentElement !== ev.currentTarget) {
          ev.currentTarget.appendChild(draggedElem);
          draggedElem.setAttribute('draggable', 'false');
          solvedColor++;
          showFactColor(dropColor);
          if (solvedColor === 3) {
            document.getElementById('fact-color').innerHTML += "<br><strong>Great job! You matched all colors!</strong>";
          }
        }
      } else {
        alert("Try matching the same colors.");
      }
    }
    function showFactColor(color) {
      const facts = {
        red: "Red means stop! Always pay attention to red signals.",
        blue: "Blue is calm like the sky and ocean.",
        yellow: "Yellow is bright like the sun and means be careful!"
      };
      document.getElementById('fact-color').innerText = facts[color];
    }
  
    // --- Game 2: Shape Matching ---
function allowDrop(ev) {
ev.preventDefault();
}

function dragShape(ev) {
  ev.dataTransfer.setData("text", ev.target.id);
}

function dropShape(ev) {
  ev.preventDefault();
  const draggedId = ev.dataTransfer.getData("text");
  const draggedEl = document.getElementById(draggedId);
  const expectedShape = ev.target.dataset.shape;
  const actualShape = draggedEl.dataset.shape;

  if (expectedShape === actualShape) {
    ev.target.appendChild(draggedEl);
    document.getElementById("fact-shape").innerText = `Great job! That’s a ${actualShape}!`;
  } else {
    document.getElementById("fact-shape").innerText = `Oops! Try again.`;
  }
}

  
    // --- Game 3: Counting ---
    function checkCount(userCount) {
      const correctCount = 5;
      const resultDiv = document.getElementById('counting-result');
      if (userCount === correctCount) {
        resultDiv.innerHTML = "Great counting! You got it right!";
      } else {
        resultDiv.innerHTML = "Oops, try again!";
      }
    }
  
    // --- Game 4: Animal Sounds ---
    function playSound(animal) {
      const resultDiv = document.getElementById('animal-guess-result');
      resultDiv.innerHTML = "";
      const audio = document.getElementById(animal + "-sound");
      audio.play();
      setTimeout(() => {
        resultDiv.innerHTML = `That was a ${animal}!`;
      }, 1500);
    }
  
    // --- Game 5: Memory Game ---
    const cards = document.querySelectorAll('.memory-card');
    let flippedCards = [];
    let matchedCount = 0;
    cards.forEach(card => {
      card.addEventListener('click', () => {
        if (card.classList.contains('flipped') || card.classList.contains('matched') || flippedCards.length === 2) return;
  
        card.classList.add('flipped');
        flippedCards.push(card);
  
        if (flippedCards.length === 2) {
          if (flippedCards[0].dataset.animal === flippedCards[1].dataset.animal) {
            flippedCards.forEach(c => c.classList.add('matched'));
            matchedCount++;
            if (matchedCount === cards.length / 2) {
              document.getElementById('memory-result').innerText = "You found all pairs! Well done!";
            }
            flippedCards = [];
          } else {
            setTimeout(() => {
              flippedCards.forEach(c => c.classList.remove('flipped'));
              flippedCards = [];
            }, 1000);
          }
        }
      });
    });
  </script>
  

</body>
</html>

///code for page 2 ( 6--9 age)

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>SmartKids Puzzle Adventure - Ages 6-9</title>
<style>
  body {
    font-family: 'Comic Sans MS', sans-serif;
    background: #e8f5e9;
    margin: 0;
    padding: 20px;
    text-align: center;
  }
  h1 {
    color: #43a047;
  }
  .game-buttons {
    margin-bottom: 30px;
  }
  .game-buttons button {
    margin: 5px;
    padding: 15px 25px;
    font-size: 1.2rem;
    border-radius: 15px;
    border: none;
    cursor: pointer;
    background-color: #81c784;
    transition: background-color 0.3s, transform 0.3s;
  }
  .game-buttons button:hover,
  .game-buttons button.active {
    background-color: #66bb6a;
    transform: scale(1.1);
  }
  .game-section {
    display: none;
    max-width: 700px;
    margin: 0 auto;
    background: #fff;
    padding: 20px;
    border-radius: 20px;
    box-shadow: 0 0 10px #aaa;
    min-height: 350px;
  }
  .game-section.active {
    display: block;
  }

  /* Memory Match */
  .memory-grid {
    display: grid;
    grid-template-columns: repeat(4, 80px);
    grid-gap: 15px;
    justify-content: center;
  }
  .memory-card {
    width: 80px;
    height: 80px;
    background: #a5d6a7;
    border-radius: 15px;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 2.5rem;
    user-select: none;
    color: transparent;
    transition: background-color 0.3s;
  }
  .memory-card.flipped,
  .memory-card.matched {
    color: black;
    background: #c8e6c9;
    cursor: default;
  }

  /* Quiz */
  .quiz-question {
    font-size: 1.3rem;
    margin-bottom: 15px;
  }
  .quiz-options button {
    margin: 5px;
    padding: 10px 20px;
    font-size: 1.1rem;
    border-radius: 12px;
    border: 1px solid #4caf50;
    background: #a5d6a7;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  .quiz-options button:hover {
    background-color: #81c784;
  }
  .quiz-feedback {
    margin-top: 20px;
    font-size: 1.2rem;
    min-height: 40px;
  }

  /* Sequence Puzzle */
  .sequence-container {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 15px;
    flex-wrap: wrap;
  }
  .seq-item {
    width: 80px;
    height: 80px;
    background: #aed581;
    border-radius: 15px;
    font-size: 2rem;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: grab;
    user-select: none;
  }
  .sequence-dropzone {
    width: 80px;
    height: 80px;
    border: 3px dashed #7cb342;
    border-radius: 15px;
    margin: 5px;
  }

  /* Spot the Difference */
  .spot-diff-container {
    display: flex;
    justify-content: center;
    gap: 40px;
    flex-wrap: wrap;
  }
  .spot-diff-img {
    width: 280px;
    height: 280px;
    background-size: cover;
    border: 3px solid #4caf50;
    border-radius: 15px;
    position: relative;
    cursor: pointer;
  }
  .spot-diff-highlight {
    position: absolute;
    border: 3px solid red;
    border-radius: 10px;
    pointer-events: none;
    animation: highlightBlink 1.5s infinite;
  }
  @keyframes highlightBlink {
    0%, 100% {opacity: 1;}
    50% {opacity: 0.3;}
  }
  #spot-diff-result {
    margin-top: 15px;
    font-size: 1.2rem;
    min-height: 40px;
  }

  /* Recycling Sort */
  .recycle-items {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
    margin-bottom: 20px;
  }
  .recycle-item {
    width: 80px;
    height: 80px;
    border-radius: 15px;
    background: #aed581;
    font-size: 2.5rem;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: grab;
    user-select: none;
  }
  .bins {
    display: flex;
    justify-content: center;
    gap: 40px;
  }
  .bin {
    width: 150px;
    height: 150px;
    border: 3px solid #4caf50;
    border-radius: 20px;
    font-size: 1.3rem;
    display: flex;
    justify-content: center;
    align-items: flex-end;
    padding-bottom: 15px;
    cursor: pointer;
    user-select: none;
    background-color: #c8e6c9;
  }
  .bin.correct {
    border-color: #388e3c;
    background-color: #a5d6a7;
  }
  .bin.incorrect {
    border-color: #d32f2f;
    background-color: #ef9a9a;
  }
  #recycle-result {
    margin-top: 15px;
    font-size: 1.2rem;
    min-height: 40px;
  }
</style>
</head>
<body>

<h1>SmartKids Puzzle Adventure - Ages 6-9</h1>

<div class="game-buttons">
  <button class="active" data-game="memory-match">Memory Match</button>
  <button data-game="quiz">Awareness Quiz</button>
  <button data-game="sequence-puzzle">Sequence Puzzle</button>
  <button data-game="spot-difference">Spot the Difference</button>
  <button data-game="recycling-sort">Recycling Sort</button>
</div>

<!-- Memory Match -->
<section id="memory-match" class="game-section active">
  <p>Flip cards to find matching pairs!</p>
  <div class="memory-grid" id="memory-grid"></div>
  <div id="memory-result" style="margin-top: 15px; font-size:1.2rem; min-height:40px;"></div>
</section>

<!-- Awareness Quiz -->
<section id="quiz" class="game-section">
  <div class="quiz-question" id="quiz-question"></div>
  <div class="quiz-options" id="quiz-options"></div>
  <div class="quiz-feedback" id="quiz-feedback"></div>
  <button id="quiz-next" style="margin-top:20px; display:none;">Next Question</button>
</section>

<!-- Sequence Puzzle -->
<section id="sequence-puzzle" class="game-section">
  <p>Drag and drop the numbers to put them in order!</p>
  <div id="sequence-dropzones" class="sequence-container"></div>
  <div id="sequence-items" class="sequence-container"></div>
  <button id="sequence-check" style="margin-top:20px;">Check Sequence</button>
  <div id="sequence-feedback" style="margin-top:15px; min-height:40px; font-size:1.2rem;"></div>
</section>

<!-- Spot the Difference -->
<section id="spot-difference" class="game-section">
  <p>Click on the differences between the two pictures!</p>
  <div class="spot-diff-container">
    <div id="spot-img1" class="spot-diff-img" style="background-image:url('https://i.imgur.com/PaMk8TP.png'); position:relative;"></div>
    <div id="spot-img2" class="spot-diff-img" style="background-image:url('https://i.imgur.com/PaMk8TP_modified.png'); position:relative;"></div>
  </div>
  <div id="spot-diff-result"></div>
</section>

<!-- Recycling Sort -->
<section id="recycling-sort" class="game-section">
  <p>Drag the items to the correct recycling bin!</p>
  <div class="recycle-items" id="recycle-items"></div>
  <div class="bins">
    <div class="bin" id="bin-plastic" data-type="plastic">Plastic ♻️</div>
    <div class="bin" id="bin-paper" data-type="paper">Paper ♻️</div>
    <div class="bin" id="bin-glass" data-type="glass">Glass ♻️</div>
  </div>
  <div id="recycle-result"></div>
</section>

<script>
  // BUTTONS: Switch between game sections
  const buttons = document.querySelectorAll('.game-buttons button');
  const sections = document.querySelectorAll('.game-section');
  buttons.forEach(btn => {
    btn.addEventListener('click', () => {
      buttons.forEach(b => b.classList.remove('active'));
      sections.forEach(s => s.classList.remove('active'));
      btn.classList.add('active');
      document.getElementById(btn.dataset.game).classList.add('active');
    });
  });

  // ----- MEMORY MATCH -----
  const memoryGrid = document.getElementById('memory-grid');
  const memoryResult = document.getElementById('memory-result');
  const memoryCardsEmojis = ['🐶','🐱','🐰','🐻','🐸','🐵','🦊','🐯'];
  let memoryCards = [];
  let flippedCards = [];
  let matchedCount = 0;

  function shuffleArray(array) {
    return array.sort(() => Math.random() - 0.5);
  }

  function initMemoryMatch() {
    memoryCards = shuffleArray(memoryCardsEmojis.concat(memoryCardsEmojis));
    memoryGrid.innerHTML = '';
    flippedCards = [];
    matchedCount = 0;
    memoryResult.textContent = '';
    memoryCards.forEach((emoji, index) => {
      const card = document.createElement('div');
      card.classList.add('memory-card');
      card.dataset.emoji = emoji;
      card.dataset.index = index;
      card.textContent = emoji;
      card.style.color = 'transparent';
      card.addEventListener('click', () => flipCard(card));
      memoryGrid.appendChild(card);
    });
  }

  function flipCard(card) {
    if (flippedCards.length >= 2 || card.classList.contains('matched') || card.classList.contains('flipped')) return;
    card.classList.add('flipped');
    card.style.color = 'black';
    flippedCards.push(card);
    if (flippedCards.length === 2) {
      setTimeout(checkMemoryMatch, 1000);
    }
  }

  function checkMemoryMatch() {
    const [card1, card2] = flippedCards;
    if (card1.dataset.emoji === card2.dataset.emoji) {
      card1.classList.add('matched');
      card2.classList.add('matched');
      matchedCount += 2;
      memoryResult.textContent = 'Great! You found a pair!';
      if (matchedCount === memoryCards.length) {
        memoryResult.textContent = '🎉 Awesome! You matched all pairs!';
      }
    } else {
      card1.classList.remove('flipped');
      card2.classList.remove('flipped');
      card1.style.color = 'transparent';
      card2.style.color = 'transparent';
      memoryResult.textContent = 'Try again!';
    }
    flippedCards = [];
  }

  initMemoryMatch();

  // ----- AWARENESS QUIZ -----
  const quizQuestions = [
    {
      question: "Which of these is safe to touch?",
      options: ["Hot stove", "Soft teddy bear", "Sharp knife", "Electric wire"],
      answer: 1
    },
    {
      question: "What should you do before crossing the road?",
      options: ["Run quickly", "Look both ways", "Close your eyes", "Shout loudly"],
      answer: 1
    },
    {
      question: "Where should you throw recyclable paper?",
      options: ["Plastic bin", "Glass bin", "Paper bin", "Trash bin"],
      answer: 2
    },
    {
      question: "If you see someone hurt, you should:",
      options: ["Ignore", "Help or call for help", "Run away", "Laugh"],
      answer: 1
    }
  ];
  let currentQuizIndex = 0;

  const quizQuestionEl = document.getElementById('quiz-question');
  const quizOptionsEl = document.getElementById('quiz-options');
  const quizFeedbackEl = document.getElementById('quiz-feedback');
  const quizNextBtn = document.getElementById('quiz-next');

  function loadQuiz() {
    quizFeedbackEl.textContent = '';
    quizNextBtn.style.display = 'none';
    const q = quizQuestions[currentQuizIndex];
    quizQuestionEl.textContent = q.question;
    quizOptionsEl.innerHTML = '';
    q.options.forEach((opt, idx) => {
      const btn = document.createElement('button');
      btn.textContent = opt;
      btn.onclick = () => checkQuizAnswer(idx);
      quizOptionsEl.appendChild(btn);
    });
  }

  function checkQuizAnswer(selected) {
    const q = quizQuestions[currentQuizIndex];
    quizOptionsEl.querySelectorAll('button').forEach(btn => btn.disabled = true);
    if (selected === q.answer) {
      quizFeedbackEl.textContent = 'Correct! 🎉';
    } else {
      quizFeedbackEl.textContent = `Oops! The correct answer is "${q.options[q.answer]}".`;
    }
    quizNextBtn.style.display = 'inline-block';
  }

  quizNextBtn.onclick = () => {
    currentQuizIndex++;
    if (currentQuizIndex >= quizQuestions.length) {
      quizQuestionEl.textContent = 'You completed the quiz! Great job!';
      quizOptionsEl.innerHTML = '';
      quizFeedbackEl.textContent = '';
      quizNextBtn.style.display = 'none';
      currentQuizIndex = 0; // reset for replay
    } else {
      loadQuiz();
    }
  };

  loadQuiz();

  // ----- SEQUENCE PUZZLE -----
  const sequenceDropzones = document.getElementById('sequence-dropzones');
  const sequenceItems = document.getElementById('sequence-items');
  const sequenceCheckBtn = document.getElementById('sequence-check');
  const sequenceFeedback = document.getElementById('sequence-feedback');

  let numbersSequence = [3,1,4,2,5];

  function initSequencePuzzle() {
    sequenceDropzones.innerHTML = '';
    sequenceItems.innerHTML = '';
    sequenceFeedback.textContent = '';

    // Create drop zones (empty slots)
    for (let i = 0; i < numbersSequence.length; i++) {
      const dropzone = document.createElement('div');
      dropzone.classList.add('sequence-dropzone');
      dropzone.dataset.index = i;
      dropzone.ondragover = e => e.preventDefault();
      dropzone.ondrop = dropToSequence;
      sequenceDropzones.appendChild(dropzone);
    }

    // Shuffle numbers for drag items
    let shuffled = [...numbersSequence].sort(() => Math.random() - 0.5);
    shuffled.forEach(num => {
      const item = document.createElement('div');
      item.classList.add('seq-item');
      item.textContent = num;
      item.draggable = true;
      item.dataset.number = num;
      item.ondragstart = dragStartSequence;
      sequenceItems.appendChild(item);
    });
  }

  let draggedItem = null;

  function dragStartSequence(e) {
    draggedItem = e.target;
  }

  function dropToSequence(e) {
    e.preventDefault();
    const dropzone = e.currentTarget;

    // If dropzone already has a child, swap it back to items container
    if (dropzone.firstChild) {
      sequenceItems.appendChild(dropzone.firstChild);
    }
    dropzone.appendChild(draggedItem);
  }

  sequenceCheckBtn.onclick = () => {
    let correct = true;
    const dropzones = sequenceDropzones.children;
    for(let i = 0; i < dropzones.length; i++) {
      const child = dropzones[i].firstChild;
      if (!child || Number(child.dataset.number) !== numbersSequence[i]) {
        correct = false;
        break;
      }
    }
    if(correct) {
      sequenceFeedback.textContent = "Well done! You put the sequence in order! 🎉";
    } else {
      sequenceFeedback.textContent = "Oops, try again! Make sure numbers are in correct order.";
    }
  };

  initSequencePuzzle();

  // ----- SPOT THE DIFFERENCE -----
  // We use 2 images: original and modified (different spots)
  // We'll define difference spots as rectangles in img2 coordinates

  const spotImg2 = document.getElementById("./img.jpg");
  const spotDiffResult = document.getElementById('spot-diff-result');

  // Difference spots: each with x,y,width,height relative to img size (280x280)
  const differences = [
    {x: 60, y: 40, w: 40, h: 40},
    {x: 200, y: 180, w: 50, h: 40},
    {x: 120, y: 220, w: 30, h: 30},
  ];

  let foundDifferences = [];

  spotImg2.onclick = function(e) {
    if (foundDifferences.length === differences.length) return;

    const rect = spotImg2.getBoundingClientRect();
    const clickX = e.clientX - rect.left;
    const clickY = e.clientY - rect.top;

    let found = false;
    for (let i = 0; i < differences.length; i++) {
      if (foundDifferences.includes(i)) continue;
      const diff = differences[i];
      if (clickX >= diff.x && clickX <= diff.x + diff.w &&
          clickY >= diff.y && clickY <= diff.y + diff.h) {
        foundDifferences.push(i);
        highlightDifference(diff);
        found = true;
        break;
      }
    }
    if (found) {
      spotDiffResult.textContent = `Great! You found ${foundDifferences.length} of ${differences.length} differences!`;
      if (foundDifferences.length === differences.length) {
        spotDiffResult.textContent = "🎉 Awesome! You found all differences!";
      }
    } else {
      spotDiffResult.textContent = "Nope! Try clicking on other spots.";
    }
  };

  function highlightDifference(diff) {
    const highlight = document.createElement('div');
    highlight.classList.add('spot-diff-highlight');
    highlight.style.left = diff.x + 'px';
    highlight.style.top = diff.y + 'px';
    highlight.style.width = diff.w + 'px';
    highlight.style.height = diff.h + 'px';
    spotImg2.appendChild(highlight);
  }

  // --- RECYCLING SORT ---
  const recycleItemsEl = document.getElementById('recycle-items');
  const bins = document.querySelectorAll('.bin');
  const recycleResult = document.getElementById('recycle-result');

  const recycleObjects = [
    {emoji: '🥤', type: 'plastic'},  // plastic cup
    {emoji: '📰', type: 'paper'},    // newspaper
    {emoji: '🍾', type: 'glass'},    // glass bottle
    {emoji: '📦', type: 'paper'},    // cardboard box
    {emoji: '🥛', type: 'plastic'},  // plastic milk carton
    {emoji: '🍷', type: 'glass'},    // wine glass
  ];

  function initRecyclingSort() {
    recycleItemsEl.innerHTML = '';
    recycleResult.textContent = '';

    recycleObjects.sort(() => Math.random() - 0.5).forEach(obj => {
      const item = document.createElement('div');
      item.classList.add('recycle-item');
      item.textContent = obj.emoji;
      item.dataset.type = obj.type;
      item.draggable = true;
      item.ondragstart = recycleDragStart;
      recycleItemsEl.appendChild(item);
    });

    bins.forEach(bin => {
      bin.classList.remove('correct', 'incorrect');
      bin.ondragover = e => e.preventDefault();
      bin.ondrop = recycleDrop;
    });
  }

  let draggedRecycleItem = null;

  function recycleDragStart(e) {
    draggedRecycleItem = e.target;
  }

  function recycleDrop(e) {
    e.preventDefault();
    const bin = e.currentTarget;
    if (!draggedRecycleItem) return;

    if (draggedRecycleItem.dataset.type === bin.dataset.type) {
      bin.classList.add('correct');
      bin.classList.remove('incorrect');
      recycleResult.textContent = 'Good job! Item sorted correctly! 😊';
      draggedRecycleItem.remove();
    } else {
      bin.classList.add('incorrect');
      bin.classList.remove('correct');
      recycleResult.textContent = 'Oops! That item does not belong here. Try again!';
    }
    draggedRecycleItem = null;

    // Check if all items sorted
    if (recycleItemsEl.children.length === 0) {
      recycleResult.textContent = '🎉 Perfect! You sorted all items correctly!';
    }
  }

  initRecyclingSort();
</script>

</body>
</html>


///code for page 3(10-12)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>SmartKids Awareness Games (10-12)</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Comic+Neue:wght@700&display=swap');
    body {
      font-family: 'Comic Neue', cursive, sans-serif;
      background: #fffae6;
      margin: 0;
      padding: 20px;
      color: #333;
      text-align: center;
      user-select: none;
    }
    h1 {
      color: #d63f8e;
      margin-bottom: 0.3em;
      text-shadow: 1px 1px 4px #fbc7db;
    }
    .nav-buttons {
      margin-bottom: 20px;
    }
    .nav-buttons button {
      background: #f9c5d1;
      border: none;
      border-radius: 15px;
      padding: 12px 22px;
      margin: 5px;
      font-weight: bold;
      color: #7a2048;
      cursor: pointer;
      box-shadow: 0 4px 8px rgb(250 198 208 / 0.7);
      transition: background-color 0.3s ease;
    }
    .nav-buttons button:hover, .nav-buttons button.active {
      background: #d63f8e;
      color: white;
      box-shadow: 0 6px 12px rgb(214 63 142 / 0.8);
    }
    .game-container {
      max-width: 480px;
      margin: 0 auto;
      background: white;
      border-radius: 20px;
      padding: 25px;
      box-shadow: 0 10px 20px rgb(0 0 0 / 0.15);
      min-height: 300px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .question {
      font-size: 1.3rem;
      margin-bottom: 20px;
      min-height: 60px;
    }
    .answers {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
    }
    .answers button {
      background: #ffd3e0;
      border: none;
      border-radius: 15px;
      padding: 12px 18px;
      font-size: 1rem;
      font-weight: 600;
      color: #7a2048;
      cursor: pointer;
      flex: 1 1 45%;
      max-width: 180px;
      box-shadow: 0 5px 10px rgb(255 211 224 / 0.7);
      transition: background-color 0.3s ease, transform 0.2s ease;
      user-select: none;
      position: relative;
    }
    .answers button:hover:not(:disabled) {
      background-color: #d63f8e;
      color: white;
      transform: scale(1.05);
      box-shadow: 0 8px 16px rgb(214 63 142 / 0.9);
    }
    .answers button:disabled {
      cursor: default;
      opacity: 0.7;
      transform: none !important;
    }
    .feedback {
      margin-top: 18px;
      font-weight: 700;
      font-size: 1.2rem;
      min-height: 24px;
      color: #333;
      transition: all 0.3s ease;
      user-select: none;
    }
    .feedback.correct {
      color: #27ae60;
      animation: popIn 0.4s ease forwards;
    }
    .feedback.wrong {
      color: #e74c3c;
      animation: popIn 0.4s ease forwards;
    }
    @keyframes popIn {
      0% { transform: scale(0.7); opacity: 0; }
      100% { transform: scale(1); opacity: 1; }
    }
    .scoreboard {
      margin-top: 20px;
      font-weight: 700;
      color: #7a2048;
      font-size: 1.1rem;
      user-select: none;
    }
    .next-btn {
      margin-top: 25px;
      background: #d63f8e;
      border: none;
      color: white;
      font-weight: 700;
      padding: 12px 25px;
      border-radius: 20px;
      cursor: pointer;
      box-shadow: 0 6px 12px rgb(214 63 142 / 0.8);
      transition: background-color 0.3s ease;
    }
    .next-btn:hover {
      background-color: #b1306b;
    }
    .next-btn:disabled {
      background-color: #f3a1c1;
      cursor: default;
      box-shadow: none;
    }
  </style>
</head>
<body>

  <h1>SmartKids Awareness Games (Ages 10–12)</h1>
  <div class="nav-buttons" id="nav-buttons">
    <!-- Buttons added by JS -->
  </div>

  <div class="game-container" id="game-container">
    <!-- Game content added by JS -->
  </div>

  <script>
    const games = [
      {
        id: 'puberty',
        title: 'Puberty Quiz',
        questions: [
          {
            q: 'What is a common sign of puberty in girls?',
            options: ['Start of periods', 'Losing teeth', 'Growing wings', 'Becoming invisible'],
            answer: 0
          },
          {
            q: 'What happens to boys during puberty?',
            options: ['Voice gets deeper', 'Grow shorter', 'Turn blue', 'Fly'],
            answer: 0
          },
          {
            q: 'At what age does puberty usually start?',
            options: ['Around 8 to 14 years', '50 years old', '2 years old', 'At birth'],
            answer: 0
          }
        ]
      },
      {
        id: 'touch',
        title: 'Good or Bad Touch',
        questions: [
          {
            q: 'Is it okay if someone touches your private parts?',
            options: ['Yes', 'No'],
            answer: 1
          },
          {
            q: 'Who can give you a safe hug?',
            options: ['Parents or family', 'Strangers', 'Anyone on the street'],
            answer: 0
          },
          {
            q: 'If someone makes you uncomfortable, what should you do?',
            options: ['Tell a trusted adult', 'Keep quiet', 'Do nothing'],
            answer: 0
          }
        ]
      },
      {
        id: 'emotions',
        title: 'Emotion Match',
        questions: [
          {
            q: 'Which face shows "sad"? 😢',
            options: ['Happy', 'Sad', 'Angry', 'Surprised'],
            answer: 1
          },
          {
            q: 'Which face shows "angry"? 😠',
            options: ['Happy', 'Sad', 'Angry', 'Tired'],
            answer: 2
          },
          {
            q: 'Which face shows "surprised"? 😮',
            options: ['Surprised', 'Sleepy', 'Sad', 'Angry'],
            answer: 0
          }
        ]
      },
      {
        id: 'internet',
        title: 'Internet Safety',
        questions: [
          {
            q: 'What should you do if a stranger asks for your address online?',
            options: ['Tell an adult', 'Give it', 'Ignore', 'Meet them'],
            answer: 0
          },
          {
            q: 'Should you share your school name with people online?',
            options: ['Yes', 'No'],
            answer: 1
          },
          {
            q: 'Is it safe to talk to strangers online?',
            options: ['Yes', 'No'],
            answer: 1
          }
        ]
      },
      {
        id: 'decision',
        title: 'Smart Decisions',
        questions: [
          {
            q: 'Your friend wants to skip school. What do you do?',
            options: ['Say no and tell a teacher', 'Join them', 'Ignore'],
            answer: 0
          },
          {
            q: 'You find money on the ground. What do you do?',
            options: ['Keep it', 'Give it to a teacher', 'Throw it away'],
            answer: 1
          },
          {
            q: 'If someone offers you candy but you don\'t know them, what should you do?',
            options: ['Take it', 'Say no and tell a parent', 'Eat it secretly'],
            answer: 1
          }
        ]
      },
      {
        id: 'habits',
        title: 'Healthy Habits',
        questions: [
          {
            q: 'Which is a healthy habit?',
            options: ['Brushing teeth twice a day', 'Eating candy all day', 'Skipping meals'],
            answer: 0
          },
          {
            q: 'What helps you stay fit?',
            options: ['Regular exercise', 'Watching TV all day', 'Sleeping all day'],
            answer: 0
          },
          {
            q: 'How many hours of sleep do kids need?',
            options: ['8-10 hours', '2 hours', '24 hours'],
            answer: 0
          }
        ]
      },
      {
        id: 'consent',
        title: 'Consent & Safety',
        questions: [
          {
            q: 'Can you hug someone if they say "no"?',
            options: ['Yes', 'No'],
            answer: 1
          },
          {
            q: 'Someone asks you to keep a secret that makes you feel bad. What should you do?',
            options: ['Tell a trusted adult', 'Keep the secret'],
            answer: 0
          },
          {
            q: 'Is it okay to share your feelings with someone you trust?',
            options: ['Yes', 'No'],
            answer: 0
          }
        ]
      }
    ];

    const navButtonsContainer = document.getElementById('nav-buttons');
    const gameContainer = document.getElementById('game-container');

    let currentGameIndex = 0;
    let currentQuestionIndex = 0;
    let score = 0;

    function createNavButtons() {
      games.forEach((game, idx) => {
        const btn = document.createElement('button');
        btn.textContent = game.title;
        btn.id = `nav-btn-${game.id}`;
        btn.addEventListener('click', () => {
          if (currentGameIndex !== idx) {
            switchGame(idx);
          }
        });
        navButtonsContainer.appendChild(btn);
      });
      highlightActiveButton();
    }

    function highlightActiveButton() {
      games.forEach((game, idx) => {
        const btn = document.getElementById(`nav-btn-${game.id}`);
        if (idx === currentGameIndex) {
          btn.classList.add('active');
        } else {
          btn.classList.remove('active');
        }
      });
    }

    function switchGame(idx) {
      currentGameIndex = idx;
      currentQuestionIndex = 0;
      score = 0;
      highlightActiveButton();
      renderQuestion();
    }

    function renderQuestion() {
      const game = games[currentGameIndex];
      if (!game) return;

      if (currentQuestionIndex >= game.questions.length) {
        // Game finished
        gameContainer.innerHTML = `
          <h2>🎉 You finished <span style="color:#d63f8e;">${game.title}</span>!</h2>
          <p>Your score: <strong>${score} / ${game.questions.length}</strong></p>
          <button class="next-btn" id="play-again-btn">Play Again</button>
        `;
        document.getElementById('play-again-btn').addEventListener('click', () => {
          currentQuestionIndex = 0;
          score = 0;
          renderQuestion();
        });
        return;
      }

      const questionObj = game.questions[currentQuestionIndex];
      gameContainer.innerHTML = `
        <div class="question">${questionObj.q}</div>
        <div class="answers"></div>
        <div class="feedback" id="feedback"></div>
        <div class="scoreboard">Score: ${score} / ${game.questions.length}</div>
        <button class="next-btn" id="next-btn" disabled>Next</button>
      `;

      const answersDiv = gameContainer.querySelector('.answers');
      questionObj.options.forEach((opt, idx) => {
        const ansBtn = document.createElement('button');
        ansBtn.textContent = opt;
        ansBtn.addEventListener('click', () => handleAnswer(idx));
        answersDiv.appendChild(ansBtn);
      });

      document.getElementById('next-btn').addEventListener('click', () => {
        currentQuestionIndex++;
        renderQuestion();
      });
    }

    function handleAnswer(selectedIndex) {
      const game = games[currentGameIndex];
      const questionObj = game.questions[currentQuestionIndex];
      const feedbackDiv = document.getElementById('feedback');
      const nextBtn = document.getElementById('next-btn');
      const answerButtons = gameContainer.querySelectorAll('.answers button');

      // Disable all answer buttons after answer is chosen
      answerButtons.forEach(btn => btn.disabled = true);

      if (selectedIndex === questionObj.answer) {
        score++;
        feedbackDiv.textContent = '✅ Great job! That’s correct!';
        feedbackDiv.className = 'feedback correct';
      } else {
        feedbackDiv.textContent = `❌ Oops, that’s not quite right. The correct answer was: "${questionObj.options[questionObj.answer]}"`;
        feedbackDiv.className = 'feedback wrong';
      }
      // Enable Next button
      nextBtn.disabled = false;

      // Update scoreboard immediately
      const scoreboard = gameContainer.querySelector('.scoreboard');
      scoreboard.textContent = `Score: ${score} / ${game.questions.length}`;
    }

    // Initialize
    createNavButtons();
    switchGame(0);
  </script>

</body>
</html>


