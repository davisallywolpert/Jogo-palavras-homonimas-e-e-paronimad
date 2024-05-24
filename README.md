<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo Didático - Palavras Homônimas e Parônimas</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }
        #game-container {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .question {
            margin-bottom: 20px;
        }
        .option {
            display: block;
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            cursor: pointer;
            background-color: #f9f9f9;
        }
        .option:hover {
            background-color: #e9e9e9;
        }
        #result {
            margin-top: 20px;
            font-size: 18px;
            color: green;
        }
    </style>
</head>
<body>
    <div id="game-container">
        <div id="question-container" class="question"></div>
        <div id="options-container"></div>
        <div id="result"></div>
        <button onclick="nextQuestion()">Próxima Pergunta</button>
    </div>

    <script>
        const questions = [
            {
                question: "Escolha a palavra correta: Ele vai para a ___ todos os dias.",
                options: ["cella", "sela", "cela"],
                answer: 2
            },
            {
                question: "Escolha a palavra correta: A ___ do livro é muito emocionante.",
                options: ["trama", "drama", "trampa"],
                answer: 0
            },
            {
                question: "Escolha a palavra correta: O ___ vai muito bem com queijo.",
                options: ["pé", "pêra", "pera"],
                answer: 2
            },
            // Adicione mais perguntas conforme necessário
        ];

        let currentQuestion = 0;

        function loadQuestion() {
            const questionContainer = document.getElementById('question-container');
            const optionsContainer = document.getElementById('options-container');
            const resultContainer = document.getElementById('result');

            questionContainer.innerHTML = questions[currentQuestion].question;
            optionsContainer.innerHTML = '';
            resultContainer.innerHTML = '';

            questions[currentQuestion].options.forEach((option, index) => {
                const optionElement = document.createElement('div');
                optionElement.className = 'option';
                optionElement.textContent = option;
                optionElement.onclick = () => checkAnswer(index);
                optionsContainer.appendChild(optionElement);
            });
        }

        function checkAnswer(selectedOption) {
            const resultContainer = document.getElementById('result');
            if (selectedOption === questions[currentQuestion].answer) {
                resultContainer.textContent = 'Correto!';
                resultContainer.style.color = 'green';
            } else {
                resultContainer.textContent = 'Errado!';
                resultContainer.style.color = 'red';
            }
        }

        function nextQuestion() {
            currentQuestion++;
            if (currentQuestion < questions.length) {
                loadQuestion();
            } else {
                const questionContainer = document.getElementById('question-container');
                const optionsContainer = document.getElementById('options-container');
                questionContainer.innerHTML = 'Fim do jogo! Parabéns!';
                optionsContainer.innerHTML = '';
                document.getElementById('result').innerHTML = '';
            }
        }

        window.onload = loadQuestion;
    </script>
</body>
</html>
     
