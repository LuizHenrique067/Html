<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora</title>
    <style>
        /* CSS Integrado */
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }

        .calculadora {
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            padding: 20px;
            width: 260px;
        }

        .display {
            width: 100%;
            height: 50px;
            text-align: left; /* Alinhamento à esquerda */
            font-size: 1.5em;
            margin-bottom: 20px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f1f1f1;
            box-sizing: border-box;
        }

        .teclado {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .tecla {
            background-color: #f0f0f0;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 15px;
            text-align: center;
            font-size: 1.2em;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .tecla:hover {
            background-color: #f1c40f;
        }

        .tecla:active {
            background-color: #f39c12;
        }

        .tecla-operacao {
            background-color: #f9f9f9;
        }

        .tecla-operacao:hover {
            background-color: #e67e22;
        }

        .tecla-operacao:active {
            background-color: #d35400;
        }

        .tecla-clear {
            background-color: #e74c3c;
            color: #fff;
        }

        .tecla-clear:hover {
            background-color: #c0392b;
        }

        .tecla-clear:active {
            background-color: #e74c3c;
        }
    </style>
</head>
<body>

<div class="calculadora">
    <input type="text" id="display" class="display" disabled>
    <div class="teclado">
        <button class="tecla tecla-clear" onclick="clearDisplay()">C</button>
        <button class="tecla" onclick="appendToDisplay('7')">7</button>
        <button class="tecla" onclick="appendToDisplay('8')">8</button>
        <button class="tecla" onclick="appendToDisplay('9')">9</button>
        <button class="tecla tecla-operacao" onclick="appendToDisplay('+')">+</button>

        <button class="tecla" onclick="appendToDisplay('4')">4</button>
        <button class="tecla" onclick="appendToDisplay('5')">5</button>
        <button class="tecla" onclick="appendToDisplay('6')">6</button>
        <button class="tecla tecla-operacao" onclick="appendToDisplay('-')">-</button>

        <button class="tecla" onclick="appendToDisplay('1')">1</button>
        <button class="tecla" onclick="appendToDisplay('2')">2</button>
        <button class="tecla" onclick="appendToDisplay('3')">3</button>
        <button class="tecla tecla-operacao" onclick="appendToDisplay('*')">*</button>

        <button class="tecla" onclick="appendToDisplay('0')">0</button>
        <button class="tecla" onclick="appendToDisplay('.')">.</button>
        <button class="tecla tecla-operacao" onclick="appendToDisplay('/')">/</button>
        <button class="tecla tecla-operacao" onclick="calculate()">=</button>
    </div>
</div>

<script>
    // JavaScript Integrado
    function appendToDisplay(value) {
        document.getElementById('display').value += value;
    }

    function clearDisplay() {
        document.getElementById('display').value = '';
    }

    function calculate() {
        try {
            let result = eval(document.getElementById('display').value);
            document.getElementById('display').value = result;
        } catch (e) {
            document.getElementById('display').value = 'Erro';
        }
    }
</script>

</body>
</html>
