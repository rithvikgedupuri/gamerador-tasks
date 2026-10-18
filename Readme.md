
# 🎮 Project: Build gamesRadar and games.fun Website!

Follow this step-by-step mission checklist to build your very own gaming portal from absolute scratch, hook up a real website name, and add interactive features!

---

# 🚀 Mission 1: Deploy the Arcade Hub on a Brand-New Root Domain

Welcome to your gamerador arcade website! In this mission, you will learn How to create a new root domain.

---

### 🌐 Part A: Purchase and Point Your New Domain in GoDaddy

When you configure a root domain (the main address without subdomains), GitHub uses special **Apex IP addresses** instead of a single CNAME text record.

1. **Buy your domain:** Purchase your new domain name (e.g., `rithvikgedupuri.space`) inside your [GoDaddy Dashboard](https://godaddy.com "GoDaddy Official Website").
2. **Open the DNS settings:** Navigate to **My Products**, find your brand-new root domain, and click **Manage DNS**.
3. **Add Apex Records (A Records):** GitHub Pages uses four distinct fallback IP addresses for root domain management. Click **Add New Record** and create **four separate A Records** using these values:
   * **First Record:** Type: `A` | Name: `@` | Value: `185.199.108.153` | TTL: `Default`
   * **Second Record:** Type: `A` | Name: `@` | Value: `185.199.109.153` | TTL: `Default`
   * **Third Record:** Type: `A` | Name: `@` | Value: `185.199.110.153` | TTL: `Default`
   * **Fourth Record:** Type: `A` | Name: `@` | Value: `185.199.111.153` | TTL: `Default`
4. **Configure the www Redirect:** To make sure your website still opens if someone writes `://yourdomain.com`, find or create a `CNAME` record with these parameters:
   * **Type:** `CNAME`
   * **Name:** `www`
   * **Value:** `rithvikgedupuri.github.io.` *(Don't forget the period at the very end)*

---

## 🛠️ Mission 3: Build the games.fun website (Create Your GitHub Repository)
*First, we need a place on the internet to store your website files.*

- [ ] **Log in to GitHub:** Open your browser and go to your GitHub account.
- [ ] **Create a New Repository:** Click the **`+`** icon in the upper-right corner and select **New repository**.
- [ ] **Name Your Project:** Choose a cool name for your gaming hub (e.g., `rithvikgedupuri.github.io`).
- [ ] **Set Visibility to Public:** Ensure **Public** is selected so your friends can see your site.
- [ ] **Add a Initialize File:** Check the box that says **Add a README file**.
- [ ] **Launch:** Click the green **Create repository** button at the bottom.

---

# 🚀 Mission 4: Build a 4-Game Learning Arcade

Welcome to your next developer milestone! In this mission, you will back up your current layout, create two brand-new educational games, and deploy a responsive 4-game dashboard.

---

### 💾 Part A: Save a Backup of Your Existing Homepage
Before changing any code, it is best practice to save a backup of your working setup.

1. **Open your repository:** Go to GitHub and open your gaming hub repository.
2. **Open the file:** Click on `index.html`.
3. **Copy everything:** Click inside the code window, press `Ctrl + A` (or `Cmd + A` on Mac) to highlight everything, and copy it (`Ctrl + C` / `Cmd + C`).
4. **Save it locally:** Open a text editor on your computer (like Notepad or TextEdit), paste the code inside, and save the file on your machine as `index_backup.txt`.

---

### 🧮 Part B: Create the "Math Attack" Game (`math.html`)
This game helps practice rapid addition. Kids can later edit the code to try multiplication or use larger numbers!

1. Go back to your main repository page on GitHub.
2. Click **Add file** ➔ **Create new file**.
3. Name the file exactly: `math.html`
4. Paste the following code into the editor:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Math Attack</title>
    <style>
        body { background-color: #121214; color: #ffffff; font-family: 'Segoe UI', sans-serif; text-align: center; padding: 50px 20px; }
        .game-box { background-color: #1e1e24; border: 2px solid #03dac6; border-radius: 12px; padding: 40px; max-width: 400px; margin: 0 auto; box-shadow: 0 4px 15px rgba(0,0,0,0.5); }
        .question { font-size: 2.5rem; margin: 20px 0; font-weight: bold; color: #6200ee; background: #fff; padding: 10px; border-radius: 8px; }
        input { font-size: 1.5rem; padding: 10px; width: 60%; text-align: center; border-radius: 6px; border: none; margin-bottom: 20px; color: #000; }
        .btn { background-color: #03dac6; color: #121214; border: none; padding: 12px 25px; font-size: 1.1rem; font-weight: bold; border-radius: 6px; cursor: pointer; }
        .back-link { display: inline-block; margin-top: 25px; color: #03dac6; text-decoration: none; }
    </style>
</head>
<body>

    <div class="game-box">
        <h2>🧮 Math Attack!</h2>
        <p>Solve the problem as fast as you can to score XP!</p>
        
        <div class="question" id="problem">? + ?</div>
        <input type="number" id="answerInput" placeholder="Type answer..." autofocus>
        <br>
        <button class="btn" id="submitBtn">SUBMIT</button>
        
        <h3 style="color: #ff4757;">Score: <span id="score">0</span> XP</h3>
        
        <a href="index.html" class="back-link">⬅️ Back to Hub</a>
    </div>

    <script>
        let score = 0;
        let num1, num2, correctAnswer;

        const problemDisplay = document.getElementById('problem');
        const input = document.getElementById('answerInput');
        const submitBtn = document.getElementById('submitBtn');
        const scoreDisplay = document.getElementById('score');

        function generateQuestion() {
            // CODE CHALLENGE: Change the 10 to 50 or 100 to make the numbers bigger!
            num1 = Math.floor(Math.random() * 10) + 1;
            num2 = Math.floor(Math.random() * 10) + 1;
            
            // CODE CHALLENGE: Change "+" to "*" to turn this into a multiplication game!
            correctAnswer = num1 + num2; 
            problemDisplay.innerText = `${num1} + ${num2}`;
            input.value = '';
            input.focus();
        }

        function checkAnswer() {
            if (parseInt(input.value) === correctAnswer) {
                score += 10;
                scoreDisplay.innerText = score;
                alert("🎉 Correct! +10 XP");
                generateQuestion();
            } else {
                alert("❌ Oops! Try that one again.");
            }
        }

        submitBtn.addEventListener('click', checkAnswer);
        input.addEventListener('keypress', (e) => { if (e.key === 'Enter') checkAnswer(); });

        generateQuestion();
    </script>
</body>
</html>
```
5. Scroll down and click the green **Commit changes...** button.

---

### 🔮 Part C: Create the "Number Wizard" Game (`guess.html`)
This game teaches logical estimation (guessing higher or lower) to find a hidden number between 1 and 50.

1. Go back to your main repository page on GitHub.
2. Click **Add file** ➔ **Create new file**.
3. Name the file exactly: `guess.html`
4. Paste the following code into the editor:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number Wizard</title>
    <style>
        body { background-color: #121214; color: #ffffff; font-family: 'Segoe UI', sans-serif; text-align: center; padding: 50px 20px; }
        .game-box { background-color: #1e1e24; border: 2px solid #03dac6; border-radius: 12px; padding: 40px; max-width: 400px; margin: 0 auto; }
        input { font-size: 1.5rem; padding: 10px; width: 50%; text-align: center; border-radius: 6px; border: none; margin: 20px 0; color: #000; }
        .btn { background-color: #6200ee; color: white; border: none; padding: 12px 25px; font-size: 1.1rem; border-radius: 6px; cursor: pointer; }
        .back-link { display: inline-block; margin-top: 25px; color: #03dac6; text-decoration: none; }
    </style>
</head>
<body>

    <div class="game-box">
        <h2>🔮 Number Wizard</h2>
        <p>I am thinking of a number between <strong>1 and 50</strong>. Can you find it?</p>
        
        <input type="number" id="guessInput" placeholder="??">
        <br>
        <button class="btn" id="guessBtn">GUESS</button>
        
        <h3 id="hint" style="color: #ffa502; margin-top: 20px;">Take a guess!</h3>
        <p>Attempts: <span id="attempts">0</span></p>
        
        <a href="index.html" class="back-link">⬅️ Back to Hub</a>
    </div>

    <script>
        // CODE CHALLENGE: Change 50 to 100 to expand the guessing universe range!
        const secretNumber = Math.floor(Math.random() * 50) + 1;
        let attempts = 0;

        const input = document.getElementById('guessInput');
        const button = document.getElementById('guessBtn');
        const hint = document.getElementById('hint');
        const attemptsDisplay = document.getElementById('attempts');

        button.addEventListener('click', () => {
            const userGuess = parseInt(input.value);
            attempts++;
            attemptsDisplay.innerText = attempts;

            if (userGuess === secretNumber) {
                hint.style.color = "#2ed573";
                hint.innerText = `🎉 YOU WIN! The number was ${secretNumber}! It took ${attempts} tries.`;
            } else if (userGuess < secretNumber) {
                hint.innerText = "📈 HIGHER! Try a bigger number.";
            } else if (userGuess > secretNumber) {
                hint.innerText = "📉 LOWER! Try a smaller number.";
            }
            input.value = '';
        });
    </script>
</body>
</html>
```
5. Scroll down and click the green **Commit changes...** button.

---

### Part D: 
1. Add the `clicker.html`

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clicker Mania</title>
    <style>
        body {
            background-color: #121214;
            color: #ffffff;
            font-family: sans-serif;
            text-align: center;
            padding: 50px 20px;
        }
        .game-box {
            background-color: #1e1e24;
            border: 2px solid #03dac6;
            border-radius: 12px;
            padding: 40px;
            max-width: 400px;
            margin: 0 auto;
        }
        .btn {
            background-color: #6200ee;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.2rem;
            border-radius: 8px;
            cursor: pointer;
        }
        .back-link {
            display: inline-block;
            margin-top: 20px;
            color: #03dac6;
            text-decoration: none;
        }
    </style>
</head>
<body>

    <div class="game-box">
        <h2>👾 Clicker Mania</h2>
        <div style="font-size: 2rem; color: #ff4757; margin: 20px 0;">Score: <span id="score">0</span></div>
        <button class="btn" id="clickBtn">💥 CLICK!</button>
        <br>
        <a href="index.html" class="back-link">⬅️ Back to Hub</a>
    </div>

    <script>
        let score = 0;
        document.getElementById('clickBtn').addEventListener('click', () => {
            score++;
            document.getElementById('score').innerText = score;
        });
    </script>

</body>
</html>

```

### Part E: Add `reaction.html`

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reflex Reflex</title>
    <style>
        body {
            background-color: #121214;
            color: #ffffff;
            font-family: 'Segoe UI', sans-serif;
            text-align: center;
            padding: 50px 20px;
        }
        .game-box {
            background-color: #1e1e24;
            border: 2px solid #03dac6;
            border-radius: 12px;
            padding: 40px;
            max-width: 500px;
            margin: 0 auto;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }
        #target {
            width: 200px;
            height: 200px;
            background-color: #ff4757;
            border-radius: 50%;
            margin: 30px auto;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: bold;
            user-select: none;
            transition: background 0.1s;
        }
        .back-link {
            display: inline-block;
            margin-top: 25px;
            color: #03dac6;
            text-decoration: none;
            font-weight: bold;
        }
        .back-link:hover { text-decoration: underline; }
    </style>
</head>
<body>

    <div class="game-box">
        <h2>⚡ Reflex Tester</h2>
        <p>Wait for the red circle to turn <strong>GREEN</strong>, then click it as fast as you can!</p>
        
        <div id="target">CLICK TO START</div>
        
        <h3 id="result">Best Time: -- ms</h3>
        
        <a href="index.html" class="back-link">⬅️ Back to Hub</a>
    </div>

    <script>
        const target = document.getElementById('target');
        const result = document.getElementById('result');
        
        let startTime, endTime;
        let timerTimeout;
        let gameState = 'idle'; // idle, waiting, green

        target.addEventListener('click', () => {
            if (gameState === 'idle') {
                // Start the test sequence
                target.style.backgroundColor = '#ff4757';
                target.innerText = 'WAIT FOR IT...';
                result.innerText = 'Get ready...';
                gameState = 'waiting';
                
                // Random delay between 1.5 and 4 seconds
                const delay = Math.random() * 2500 + 1500;
                
                timerTimeout = setTimeout(() => {
                    target.style.backgroundColor = '#2ed573';
                    target.innerText = 'CLICK!!!';
                    startTime = Date.now();
                    gameState = 'green';
                }, delay);
                
            } else if (gameState === 'waiting') {
                // Cheated! Clicked too early
                clearTimeout(timerTimeout);
                target.style.backgroundColor = '#ffa502';
                target.innerText = 'TOO EARLY!';
                result.innerText = 'Trigger happy! Try again.';
                gameState = 'idle';
                
            } else if (gameState === 'green') {
                // Successful hit
                endTime = Date.now();
                const reactionTime = endTime - startTime;
                target.style.backgroundColor = '#6200ee';
                target.innerText = 'RESET';
                result.innerText = `Your Time: ${reactionTime} ms!`;
                gameState = 'idle';
            }
        });
    </script>

</body>
</html>

```

### 🌐 Part F: Deploy the New 4-Box Arcade Hub (`index.html`)
Now update your primary entry page to display all four games side-by-side in a clean, responsive layout.

1. Open your **`index.html`** file on GitHub.
2. Click the **Pencil icon ✏️** to edit it.
3. Completely delete everything currently inside the file.
4. Paste this full master portal layout code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arcade Portal</title>
    <style>
        body {
            background-color: #121214;
            color: #ffffff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            text-align: center;
            margin: 0;
            padding: 20px;
        }
        header {
            padding: 40px 20px;
            background: linear-gradient(135deg, #6200ee, #03dac6);
            border-radius: 12px;
            margin-bottom: 30px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }
        h1 { margin: 0; font-size: 2.5rem; text-transform: uppercase; letter-spacing: 2px; }
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            max-width: 1000px;
            margin: 0 auto;
        }
        .card {
            background-color: #1e1e24;
            border: 2px solid #333;
            border-radius: 12px;
            padding: 25px;
            transition: transform 0.2s, border-color 0.2s;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .card:hover {
            transform: translateY(-5px);
            border-color: #03dac6;
        }
        .card h3 { margin-top: 0; color: #03dac6; }
        .btn {
            display: inline-block;
            background-color: #6200ee;
            color: white;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 6px;
            font-weight: bold;
            margin-top: 15px;
        }
        .btn:hover { background-color: #3700b3; }
    </style>
</head>
<body>

    <header>
        <h1>🎮 Kid's Coding Arcade </h1>
        <p>Play the games, then open up GitHub to change how they work!</p>
    </header>

    <div class="grid">
        <!-- Game 1 -->
        <div class="card">
            <h3>Clicker Mania</h3>
            <p>Score points by clicking as fast as you can before time runs out!</p>
            <a href="clicker.html" class="btn">Play Now</a>
        </div>

        <!-- Game 2 -->
        <div class="card">
            <h3>⚡ Reflex Tester</h3>
            <p>Test your speed! Click the target the exact millisecond it flashes green.</p>
            <a href="reaction.html" class="btn" style="background-color: #03dac6; color: #121214;">Play Now</a>
        </div>

        <!-- Game 3 -->
        <div class="card">
            <h3>🧮 Math Attack!</h3>
            <p>A high-speed math quest. Rapid addition helper to gain points!</p>
            <a href="math.html" class="btn" style="background-color: #ff4757;">Play Now</a>
        </div>

        <!-- Game 4 -->
        <div class="card">
            <h3>🔮 Number Wizard</h3>
            <p>Use elimination logic to hunt down the system's hidden secret number.</p>
            <a href="guess.html" class="btn" style="background-color: #ffa502; color: #121214;">Play Now</a>
        </div>
    </div>

</body>
</html>

```
---
# Mission 5: Configure Custom Domains to Root Domain

To point your new subdomain (`games.fun.rithvikgedupuri.space`) to your GitHub Pages site, you need to configure settings in both your **GoDaddy DNS panel** and your **GitHub repository**. 

## Step 1: Add a CNAME Record in GoDaddy
1. Click the black **Add New Record** button located right above your DNS records table.
2. Fill out the fields with the following details:
   * **Type:** `CNAME`
   * **Name:** `games.fun`
   * **Value (or Data):** `rithvikgedupuri.github.io.` *(Note: Match this to the target username displayed in your existing `www` record)*
   * **TTL:** `1 Hour` (or default)
3. Save the record.

## Step 2: Configure Your GitHub Repository
1. Go to the GitHub repository containing the project you want this subdomain to display.
2. Click on **Settings** (the gear icon at the top of the repository).
3. Scroll down to the **Pages** section in the left sidebar.
4. Under **Custom domain**, type your complete subdomain: `games.fun.rithvikgedupuri.space`.
5. Click **Save**.

## Step 3: Enforce HTTPS
* Once GitHub successfully verifies your domain ownership (this usually takes a few minutes to an hour), check the box for **Enforce HTTPS** in that same GitHub Pages settings menu.

---

### 🚀 Part A: Create Your Repository and Restore Code

1. **Log in to GitHub:** Open your browser and go to your GitHub account.
2. **Create a New Repository:** Click the `+` icon in the upper-right corner and select **New repository**.
3. **Name Your Project:** Choose a cool name for your gaming hub (e.g., `gamerador`).
4. **Set Visibility to Public:** Ensure **Public** is selected so your friends can see your site.
5. **Add an Initialize File:** Check the box that says **Add a README file**.
6. **Launch:** Click the green **Create repository** button at the bottom.
7. **Create the Main Page:** Inside your new repository, click **Add file** ➔ **Create new file**. Name the file exactly `index.html`.
8. add the following content

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game Radar - Discover & Review Games</title>
    <style>
        :root {
            --bg-color: #0f172a;
            --card-bg: #1e293b;
            --accent-color: #38bdf8;
            --accent-hover: #0ea5e9;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --border-color: #334155;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            margin-bottom: 30px;
            padding: 20px;
            background: var(--card-bg);
            border-radius: 12px;
            border: 1px solid var(--border-color);
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
        }

        header h1 {
            color: var(--accent-color);
            font-size: 2.5rem;
            margin-bottom: 10px;
        }

        header p {
            color: var(--text-muted);
        }

        section {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 12px;
            border: 1px solid var(--border-color);
            margin-bottom: 25px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
        }

        h2 {
            color: var(--accent-color);
            margin-bottom: 15px;
            font-size: 1.5rem;
        }

        /* Search Section Styles */
        .search-container {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
        }

        .search-box {
            flex: 1;
            padding: 12px 15px;
            font-size: 1rem;
            background: var(--bg-color);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            border-radius: 8px;
            outline: none;
            transition: border-color 0.2s;
        }

        .search-box:focus {
            border-color: var(--accent-color);
        }

        .game-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 15px;
            max-height: 400px;
            overflow-y: auto;
            padding-right: 5px;
        }

        .game-card {
            background: var(--bg-color);
            padding: 15px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            transition: transform 0.2s, border-color 0.2s;
        }

        .game-card:hover {
            transform: translateY(-3px);
            border-color: var(--accent-color);
        }

        .game-card h3 {
            font-size: 1.1rem;
            margin-bottom: 5px;
            color: var(--text-main);
        }

        .game-card span {
            font-size: 0.85rem;
            color: var(--accent-color);
            background: rgba(56, 189, 248, 0.1);
            padding: 2px 8px;
            border-radius: 4px;
            display: inline-block;
        }

        /* Form Controls */
        label {
            display: block;
            margin-bottom: 8px;
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        select, input[type="text"], textarea {
            width: 100%;
            padding: 10px 12px;
            background: var(--bg-color);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            border-radius: 8px;
            margin-bottom: 15px;
            font-size: 1rem;
        }

        button {
            background: var(--accent-color);
            color: var(--bg-color);
            border: none;
            padding: 12px 20px;
            font-weight: bold;
            font-size: 1rem;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.2s;
            width: 100%;
        }

        button:hover {
            background: var(--accent-hover);
        }

        #quiz-result {
            margin-top: 15px;
            font-weight: bold;
            color: var(--accent-color);
            font-size: 1.1rem;
        }

        .review-item {
            background: var(--bg-color);
            padding: 12px 15px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            margin-top: 10px;
        }

        .review-item strong {
            color: var(--accent-color);
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <h1>📡 Game Radar</h1>
            <p>Your interactive hub for top games & community reviews!</p>
        </header>

        <!-- SEARCH & FILTER SECTION -->
        <section>
            <h2>🔍 Search Games Database</h2>
            <div class="search-container">
                <input type="text" id="searchInput" class="search-box" placeholder="Search PUBG, Minecraft, Roblox, FC Mobile...">
                <button onclick="filterGames()" style="width: auto;">Search</button>
            </div>
            <!-- Dynamically populated game grid -->
            <div id="gameGrid" class="game-grid"></div>
        </section>

        <!-- QUIZ SECTION -->
        <section>
            <h2>🎮 Game Finder Quiz</h2>
            <label for="genreSelect">Choose your favorite genre:</label>
            <select id="genreSelect">
                <option value="Sandbox">Sandbox & Survival</option>
                <option value="Open World">Open World / Adventure</option>
                <option value="Action">Action & Shooter</option>
                <option value="Party">Party & Multiplayer</option>
                <option value="Mobile">Mobile & Sports</option>
                <option value="Horror">Horror & Survival</option>
                <option value="Fighting">Fighting & Arcade</option>
                <option value="Racing">Racing & Sports</option>
            </select>
            <button onclick="recommendGame()">Find My Game!</button>
            <div id="quiz-result"></div>
        </section>

        <!-- Start of Top 5 Game List -->
        <section>
            <h2>🏆 My Top 5 Games of the Year</h2>
            <p style="color: var(--text-muted); margin-bottom: 15px;">Here are my absolute favorite games right now and exactly why you should play them:</p>

            <ol style="font-size: 16px; line-height: 1.8; color: var(--text-main); padding-left: 20px;">
              <li>🚀 <strong>PUBG Mobile</strong> - Intense battle royale survival gameplay with friends!</li>
              <li>🧱 <strong>Minecraft</strong> - Endless building options and infinite sandbox exploration.</li>
              <li>👑 <strong>Roblox</strong> - Millions of custom player-created minigames to try out.</li>
              <li>🏎️ <strong>EA Sports FC Mobile</strong> - Build your ultimate dream team and rank up in Head-to-Head mode!</li>
              <li>👾 <strong>Among Us</strong> - Keep your eyes open and spot the imposter before it's too late!</li>
            </ol>
        </section>
        <!-- End of Top 5 Game List -->

        <!-- Start of Voting Poll Section -->
        <section style="text-align: center;">
            <hr style="margin: 0 0 20px 0; border: 1px solid var(--border-color);">

            <h2 style="margin-top: 0;">📊 Cast Your Vote!</h2>
            <p style="color: var(--text-muted); margin-bottom: 15px;">Help me settle the debate! Vote for your favorite game on my official poll:</p>
            
            <a href="https://strawpoll.com/poy9k1qOOgJ" target="_blank" style="display: inline-block; background-color: var(--accent-color); color: var(--bg-color); padding: 12px 24px; text-decoration: none; font-weight: bold; border-radius: 8px; transition: background 0.2s;">👉 Click Here to Vote Now! 👈</a>
        </section>
        <!-- End of Voting Poll Section -->

        <!-- REVIEW SUBMISSION SECTION -->
        <section>
            <h2>✍️ Community Reviews</h2>
            <label for="gameTitle">Game Title</label>
            <input type="text" id="gameTitle" placeholder="Game Title">
            
            <label for="reviewText">Your Review</label>
            <textarea id="reviewText" rows="3" placeholder="Write your review here..."></textarea>
            
            <button onclick="submitReview()">Submit Review</button>
            
            <div style="margin-top: 20px;">
                <h3>Recent Reviews:</h3>
                <div id="reviewList">
                    <div class="review-item">
                        <strong>Minecraft</strong>
                        <p>Infinite creativity and survival fun!</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <script>
        // Game Database Array
        const gamesDatabase = [
            { title: "PUBG Mobile", genre: "Action & Shooter" },
            { title: "Minecraft", genre: "Sandbox & Survival" },
            { title: "Roblox", genre: "Sandbox & Survival" },
            { title: "EA Sports FC Mobile", genre: "Mobile & Sports" },
            { title: "Among Us", genre: "Party & Multiplayer" },
            { title: "Fortnite", genre: "Action & Shooter" },
            { title: "Valorant", genre: "Action & Shooter" },
            { title: "Zelda: Tears of the Kingdom", genre: "Open World / Adventure" },
            { title: "Grand Theft Auto V", genre: "Open World / Action" },
            { title: "Call of Duty: Warzone", genre: "Action & Shooter" },
            { title: "Counter-Strike 2", genre: "Action & Shooter" },
            { title: "League of Legends", genre: "Action & Strategy" },
            { title: "Apex Legends", genre: "Action & Shooter" },
            { title: "Rocket League", genre: "Racing & Sports" },
            { title: "Fall Guys", genre: "Party & Multiplayer" },
            { title: "Terraria", genre: "Sandbox & Survival" },
            { title: "Stardew Valley", genre: "Sandbox & Survival" },
            { title: "Genshin Impact", genre: "Open World / Adventure" },
            { title: "Elden Ring", genre: "Open World / Adventure" },
            { title: "Baldur's Gate 3", genre: "Open World / Adventure" },
            { title: "EA Sports FC 24", genre: "Racing & Sports" },
            { title: "Super Smash Bros. Ultimate", genre: "Fighting & Arcade" },
            { title: "Mario Kart 8 Deluxe", genre: "Racing & Sports" },
            { title: "Animal Crossing: New Horizons", genre: "Sandbox & Survival" },
            { title: "Cyberpunk 2077", genre: "Open World / Adventure" },
            { title: "Overwatch 2", genre: "Action & Shooter" },
            { title: "Portal 2", genre: "Party & Multiplayer" },
            { title: "Undertale", genre: "Open World / Adventure" },
            { title: "Pokemon Scarlet and Violet", genre: "Open World / Adventure" },
            { title: "Team Fortress 2", genre: "Action & Shooter" },
            { title: "Hades", genre: "Action & Shooter" },
            { title: "Subnautica", genre: "Horror & Survival" },
            { title: "Phasmophobia", genre: "Horror & Survival" },
            { title: "Dead by Daylight", genre: "Horror & Survival" },
            { title: "Resident Evil 4", genre: "Horror & Survival" },
            { title: "Mortal Kombat 1", genre: "Fighting & Arcade" },
            { title: "Street Fighter 6", genre: "Fighting & Arcade" },
            { title: "Tekken 8", genre: "Fighting & Arcade" },
            { title: "Forza Horizon 5", genre: "Racing & Sports" },
            { title: "Gran Turismo 7", genre: "Racing & Sports" },
            { title: "Need for Speed Unbound", genre: "Racing & Sports" },
            { title: "The Last of Us Part I", genre: "Horror & Survival" }
        ];

        // Function to display games on the page
        function displayGames(gamesArray) {
            let grid = document.getElementById('gameGrid');
            grid.innerHTML = "";

            if (gamesArray.length === 0) {
                grid.innerHTML = "<p style='color: var(--text-muted);'>No games found matching your search.</p>";
                return;
            }

            gamesArray.forEach(game => {
                let card = document.createElement('div');
                card.className = 'game-card';
                card.innerHTML = `<h3>${game.title}</h3><span>${game.genre}</span>`;
                grid.appendChild(card);
            });
        }

        // Search Function triggered by button
        function filterGames() {
            let input = document.getElementById('searchInput').value.toLowerCase();
            let filtered = gamesDatabase.filter(game => 
                game.title.toLowerCase().includes(input) || 
                game.genre.toLowerCase().includes(input)
            );
            displayGames(filtered);
        }

        // Quiz Recommendation Logic
        function recommendGame() {
            let genre = document.getElementById('genreSelect').value;
            let resultDiv = document.getElementById('quiz-result');
            resultDiv.innerText = "Showing top picks for " + genre + " in the database above!";
        }

        // Review Submission Logic
        function submitReview() {
            let title = document.getElementById('gameTitle').value.trim();
            let text = document.getElementById('reviewText').value.trim();
            let reviewList = document.getElementById('reviewList');

            if (title === "" || text === "") {
                alert("Please fill out both fields!");
                return;
            }

            let newReview = document.createElement('div');
            newReview.className = 'review-item';
            newReview.innerHTML = `<strong>${title}</strong><p>${text}</p>`;

            reviewList.prepend(newReview);

            document.getElementById('gameTitle').value = "";
            document.getElementById('reviewText').value = "";
        }

        // Initial load to show games when page opens
        window.onload = function() {
            displayGames(gamesDatabase);
        };
    </script>
</body>
</html>
```



### 🌐 Mission-6: Connect Your Custom Domain to GitHub Pages

Once your repository has your code, you need to point your custom domain to your newly created GitHub project.

1. **Open repository settings:** Inside your `gameradar` repository, click on the ⚙️ **Settings** tab at the top.
2. **Navigate to Pages:** On the left sidebar menu, click on **Pages** under the "Code and automation" block.
3. **Configure the custom domain:** Scroll down to the **Custom domain** section, type your domain address `gameradar.rameshgedupuri.space` into the text box, and click **Save**.
4. **Enforce security:** Wait a few moments for GitHub to verify the site, then check the box next to **Enforce HTTPS** to keep your website secure.


### 💻 Part A: Assign the Root Domain inside GitHub Pages

Now, update your repository settings so GitHub recognizes requests hitting those four IP addresses.

1. **Access your codebase:** Go to [GitHub](https://github.com "GitHub Homepage") and open your arcade project repository (e.g., `gamerador`).
2. **Open routing paths:** Click on the ⚙️ **Settings** tab located along the top layout menu bar.
3. **Navigate to Pages:** From the left sidebar options list, select **Pages** inside the "Code and automation" block.
4. **Bind your custom URL:** Scroll down to the **Custom domain** field, clear out any old references, and type your new root domain cleanly:
   `mycoolarcade.com` *(Replace this with the actual domain name you bought)*
5. **Save changes:** Click **Save**. GitHub will automatically insert a clean `CNAME` confirmation text file straight into your main code branch directory.

---

### 🔒 Part B: Issue SSL and Verify

1. **Enforce HTTPS Encryption:** Right under your saved custom domain path, check the box for **Enforce HTTPS**. 
   * *Note: If it is unclickable, wait roughly 10 minutes. GitHub is actively pinging GoDaddy's four new A-records to safely issue a free SSL security certificate.*
2. **Live Test:** Once the status dot flips from yellow to a green checkmark, open a clean browser view and load your new root domain address to enjoy your standalone arcade network!

   
### 🏆 MISSION COMPLETE STATUS

```text
======================================================================
  🎮 PLAYER 1: infinitetechstack              [ LEVEL 10 MAX ACHIEVED ]
======================================================================

  [✓] GoDaddy Apex Routing Records ........................... SECURED!
  [✓] GitHub Pages Deployment Engine ......................... ALIGNED!
  [✓] SSL Global Security Protocol ......................... ENFORCED!
  [✓] Custom Standalone Website Portal ......................... LIVE!

  ------------------------------------------------------------------
  🎉 CONGRATULATIONS, Master Rithvik!
  ------------------------------------------------------------------
  You have successfully transitioned from a nested project directory 
  to a fully-branded, global-facing gaming platform. Your servers 
  are active, your code is clean, and your arcade network is officially 
  broadcasting worldwide on its own root domain!
======================================================================
```


