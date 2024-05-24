# Jogo-palavras-homonimas-e-paronimas
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo Didático: Palavras Homônimas e Parônimas</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Jogo Didático: Palavras Homônimas e Parônimas</h1>
        <div id="question-container">
            <p id="question"></p>
            <div id="options-container">
                <button class="option-btn" onclick="checkAnswer(0)">Opção 1</button>
                <button class="option-btn" onclick="checkAnswer(1)">Opção 2</button>
                <button class="option-btn" onclick="checkAnswer(2)">Opção 3</button>
                <button class="option-btn" onclick="checkAnswer(3)">Opção 4</button>
            </div>
        </div>
        <div id="result-container">
            <p id="result"></p>
            <button id="next-btn" onclick="nextQuestion()">Próxima Pergunta</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
