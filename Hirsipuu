<!DOCTYPE html>
<html lang="fi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hirsipuu - KUNDSERVICE</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #add8e6;
            text-align: center;
        }
        .game-container {
            margin-top: 50px;
            font-size: 24px;
        }
        .hint, .result {
            font-size: 20px;
            margin: 10px;
            font-weight: bold;
        }
        .word {
            font-size: 40px;
            letter-spacing: 5px;
            color: #ff6347;
        }
        .emoji {
            font-size: 50px;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <div class="hint">Vinkki: Sana liittyy asiakaspalveluun</div>
        <div class="word" id="wordDisplay">_ _ _ _ _ _ _ _ _ _</div>
        <input type="text" id="guessInput" maxlength="1" placeholder="Arvaa kirjain">
        <button onclick="guessLetter()">Arvaa</button>
        <p>Virheet: <span id="mistakes">0</span>/10</p>
        <div class="result" id="result"></div>
        <div class="emoji" id="emoji"></div>
    </div>

    <script>
        const word = 'KUNDSERVICE';
        let guessedLetters = [];
        let incorrectGuesses = 0;
        const maxMistakes = 10;

        function displayWord() {
            let display = '';
            for (const letter of word) {
                display += guessedLetters.includes(letter) ? letter + ' ' : '_ ';
            }
            document.getElementById('wordDisplay').textContent = display.trim();
        }

        function guessLetter() {
            const input = document.getElementById('guessInput').value.toUpperCase();
            document.getElementById('guessInput').value = '';

            if (input && /^[A-Z]$/.test(input) && !guessedLetters.includes(input)) {
                if (word.includes(input)) {
                    guessedLetters.push(input);
                    displayWord();
                    checkWin();
                } else {
                    incorrectGuesses++;
                    document.getElementById('mistakes').textContent = incorrectGuesses;
                    checkLoss();
                }
            }
        }

        function checkWin() {
            if (word.split('').every(letter => guessedLetters.includes(letter))) {
                document.getElementById('result').textContent = 'Sana on arvattu oikein!';
                document.getElementById('emoji').textContent = '😀';
            }
        }

        function checkLoss() {
            if (incorrectGuesses >= maxMistakes) {
                document.getElementById('result').textContent = `Peli päättyi, oikea sana on ${word}`;
                document.getElementById('emoji').textContent = '😞';
            }
        }

        displayWord();
    </script>
</body>
</html>
