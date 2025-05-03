# kalkulator_ilmiah
make kalkulator 
<!DOCTYPE html>
<html>
<head>
    <title>Kalkulator Ilmiah</title>
    <style>
        body {
            font-family: sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: #f0f0f0;
        }

        .calculator {
            border: 1px solid #ccc;
            padding: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            width: 350px;
        }

        #display {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1.8em;
            text-align: right;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            grid-gap: 5px;
        }

        button {
            padding: 10px;
            font-size: 1.2em;
            border: 1px solid #ddd;
            border-radius: 4px;
            background-color: #f9f9f9;
            cursor: pointer;
        }

        button:hover {
            background-color: #eee;
        }

        .operator {
            background-color: #e0f7fa;
        }

        .equal {
            background-color: #c8e6c9;
        }
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" readonly>
    <div class="buttons">
        <button onclick="clearDisplay()">C</button>
        <button onclick="addToDisplay('sin(')">sin</button>
        <button onclick="addToDisplay('cos(')">cos</button>
        <button onclick="addToDisplay('tan(')">tan</button>
        <button onclick="addToDisplay('log(')">log</button>
        <button onclick="addToDisplay('7')">7</button>
        <button onclick="addToDisplay('8')">8</button>
        <button onclick="addToDisplay('9')">9</button>
        <button onclick="addToDisplay('/')" class="operator">/</button>
        <button onclick="addToDisplay('sqrt(')">√</button>
        <button onclick="addToDisplay('4')">4</button>
        <button onclick="addToDisplay('5')">5</button>
        <button onclick="addToDisplay('6')">6</button>
        <button onclick="addToDisplay('*')" class="operator">*</button>
        <button onclick="addToDisplay('^(')">^</button>
        <button onclick="addToDisplay('1')">1</button>
        <button onclick="addToDisplay('2')">2</button>
        <button onclick="addToDisplay('3')">3</button>
        <button onclick="addToDisplay('-')" class="operator">-</button>
        <button onclick="addToDisplay('pi')">π</button>
        <button onclick="addToDisplay('0')">0</button>
        <button onclick="addToDisplay('.')">.</button>
        <button onclick="calculate()" class="equal">=</button>
        <button onclick="addToDisplay('+')" class="operator">+</button>
        <button onclick="addToDisplay('e')">e</button>
        <button onclick="memoryAdd()">M+</button>
        <button onclick="memorySubtract()">M-</button>
        <button onclick="memoryClear()">MC</button>
        <button onclick="memoryRecall()">MR</button>
    </div>
</div>

<script>
    let memory = 0;

    function addToDisplay(value) {
        if (value === 'pi') {
            document.getElementById('display').value += Math.PI;
        } else if (value === 'e') {
            document.getElementById('display').value += Math.E;
        } else {
            document.getElementById('display').value += value;
        }
    }

    function clearDisplay() {
        document.getElementById('display').value = '';
    }

    function calculate() {
        try {
            document.getElementById('display').value = eval(document.getElementById('display').value);
        } catch (error) {
            document.getElementById('display').value = 'Error';
        }
    }

    function memoryAdd() {
        memory += parseFloat(document.getElementById('display').value) || 0;
    }

    function memorySubtract() {
        memory -= parseFloat(document.getElementById('display').value) || 0;
    }

    function memoryClear() {
        memory = 0;
    }

    function memoryRecall() {
        document.getElementById('display').value = memory;
    }
</script>

</body>
</html>
