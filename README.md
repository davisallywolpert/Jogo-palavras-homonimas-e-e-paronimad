<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo de Palavras Homônimas e Parônimas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 10px 0;
        }
        main {
            padding: 20px;
        }
        .question {
            margin: 20px 0;
        }
        .btn {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 10px;
            cursor: pointer;
            font-size: 16px;
        }
        .btn:hover {
            background-color: #45a049;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Jogo de Palavras Homônimas e Parônimas</h1>
    </header>
    <main>
        <div class="question">
            <p id="word-pair">Clique em "Iniciar" para começar!</p>
        </div>
        <button class="btn" onclick="checkAnswer('homonima')">Homônima</button>
        <button class="btn" onclick="checkAnswer('paronima')">Parônima</button>
        <div class="result" id="result"></div>
        <button class="btn" onclick="startGame()">Iniciar</button>
    </main>

    <script>
        const pairs = [
            { words: "censo / senso", type: "paronima" },
            { words: "acento / assento", type: "paronima" },
            { words: "cela / sela", type: "paronima" },
            { words: "cego / sego", type: "paronima" },
            { words: "cela / sela", type: "paronima" },
            { words: "tacha / taxa", type: "paronima" },
            { words: "acender / ascender", type: "paronima" },
            { words: "cela / sela", type: "paronima" },
            { words: "chá / xá", type: "homonima" },
            { words: "cela / sela", type: "paronima" },
            { words: "cego / sego", type: "paronima" },
            { words: "cozer / coser", type: "paronima" },
            { words: "dúvida / dívida", type: "paronima" },
            { words: "elogio / alogio", type: "paronima" },
            { words: "emigrar / imigrar", type: "paronima" },
            { words: "emergir / imergir", type: "paronima" },
            { words: "flagrante / fragrante", type: "paronima" },
            { words: "inflação / infração", type: "paronima" },
            { words: "ratificar / retificar", type: "paronima" },
            { words: "tacha / taxa", type: "paronima" }
        ];

        let currentPair = {};

        function startGame() {
            document.getElementById("result").textContent = "";
            currentPair = pairs[Math.floor(Math.random() * pairs.length)];
            document.getElementById("word-pair").textContent = currentPair.words;
        }

        function checkAnswer(answer) {
            if (currentPair.type === answer) {
                document.getElementById("result").textContent = "Correto! " + currentPair.words + " são palavras " + currentPair.type + "s.";
            } else {
                document.getElementById("result").textContent = "Errado! " + currentPair.words + " são palavras " + currentPair.type + "s.";
            }
            setTimeout(startGame, 2000);
        }
    </script>
</body>
</html>

