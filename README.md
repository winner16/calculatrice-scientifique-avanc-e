
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculatrice Scientifique Avancée</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            text-align: center;
            padding: 20px;
            color: black;
        }
        #calculator {
            display: inline-block;
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border: 2px solid #007bff;
        }
        input[type="text"] {
            width: 100%;
            height: 40px;
            font-size: 24px;
            text-align: right;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 5px;
        }
        button {
            width: 60px;
            height: 60px;
            font-size: 20px;
            margin: 5px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            background-color: #007bff;
            color: white;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>

    <h1>Calculatrice Scientifique Avancée</h1>
    <div id="calculator">
        <input type="text" id="display" disabled>
        <br>
        <button onclick="clearDisplay()">C</button>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button onclick="appendToDisplay('/')">/</button>
        <br>
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button onclick="appendToDisplay('*')">*</button>
        <br>
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button onclick="appendToDisplay('-')">-</button>
        <br>
        <button onclick="appendToDisplay('0')">0</button>
        <button onclick="calculate()">=</button>
        <button onclick="appendToDisplay('+')">+</button>
        <button onclick="calculate('sqrt')">√</button>
        <br>
        <button onclick="calculate('sin')">sin</button>
        <button onclick="calculate('cos')">cos</button>
        <button onclick="calculate('tan')">tan</button>
        <button onclick="calculate('log')">log</button>
        <button onclick="calculate('exp')">exp</button>
    </div>

    <script>
        function appendToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculate(operation) {
            let display = document.getElementById('display');
            let result;

            try {
                if (operation === 'sqrt') {
                    result = Math.sqrt(eval(display.value));
                } else if (operation === 'sin') {
                    result = Math.sin(eval(display.value) * Math.PI / 180);
                } else if (operation === 'cos') {
                    result = Math.cos(eval(display.value) * Math.PI / 180);
                } else if (operation === 'tan') {
                    result = Math.tan(eval(display.value) * Math.PI / 180);
                } else if (operation === 'log') {
                    result = Math.log(eval(display.value));
                } else if (operation === 'exp') {
                    result = Math.exp(eval(display.value));
                } else {
                    result = eval(display.value);
                }
                display.value = result;
            } catch (error) {
                display.value = 'Erreur';
            }
        }
    </script>

</body>
</html>
