# CodSofttask3webdevelopment
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
        }

        #calculator {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 8px;
            max-width: 300px;
            margin: auto;
            padding: 16px;
            border: 1px solid #ccc;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        #display {
            grid-column: span 4;
            text-align: right;
            padding: 8px;
            font-size: 1.5em;
        }

        button {
            padding: 12px;
            font-size: 1em;
            cursor: pointer;
        }
    </style>
</head>

<body>

    <div id="calculator">
        <div id="display">0</div>
        <button onclick="clearDisplay()">C</button>
        <button onclick="appendInput('7')">7</button>
        <button onclick="appendInput('8')">8</button>
        <button onclick="appendInput('9')">9</button>
        <button onclick="appendInput('/')">/</button>
        <button onclick="appendInput('4')">4</button>
        <button onclick="appendInput('5')">5</button>
        <button onclick="appendInput('6')">6</button>
        <button onclick="appendInput('*')">*</button>
        <button onclick="appendInput('1')">1</button>
        <button onclick="appendInput('2')">2</button>
        <button onclick="appendInput('3')">3</button>
        <button onclick="appendInput('-')">-</button>
        <button onclick="appendInput('0')">0</button>
        <button onclick="appendInput('.')">.</button>
        <button onclick="calculate()">=</button>
        <button onclick="appendInput('+')">+</button>
    </div>

    <script>
        let display = document.getElementById("display");
        let currentInput = "";

        function clearDisplay() {
            currentInput = "";
            updateDisplay();
        }

        function appendInput(value) {
            currentInput += value;
            updateDisplay();
        }

        function updateDisplay() {
            display.textContent = currentInput || "0";
        }

        function calculate() {
            try {
                currentInput = eval(currentInput).toString();
                updateDisplay();
            } catch (error) {
                currentInput = "Error";
                updateDisplay();
            }
        }
    </script>

</body>

</html>
