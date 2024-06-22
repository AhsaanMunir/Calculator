# Calculator
#The code is for calculator using html and javascrpit
<!DOCTYPE html>
<head>
<title>Modern Calculator</title>
<style>
    body {
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #f5f5f5;
        margin: 0;
    }
    .calculator {
        background-color: #333;
        border-radius: 10px;
        padding: 20px;
        box-shadow: 0 0 10px rgba(0,0,0,0.1);
        width: 300px;
        max-width: 100%;
    }
    .calculator input[type="text"] {
        width: 100%;
        height: 60px;
        font-size: 2rem;
        text-align: right;
        padding: 10px;
        box-sizing: border-box;
        background-color: #444;
        color: white;
        border: none;
        border-radius: 5px;
        margin-bottom: 10px;
    }
    .calculator .keys {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-gap: 10px;
    }
    .calculator button {
        padding: 15px;
        font-size: 1.5rem;
        background-color: #666;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s ease;
    }
    .calculator button:hover {
        background-color: #555;
    }
    .calculator button.operator {
        background-color: #FF9500;
    }
    .calculator button.operator:hover {
        background-color: #E8800C;
    }
    .calculator button.clear {
        grid-column: span 2;
        background-color: #FF3B30;
    }
    .calculator button.clear:hover {
        background-color: #E72E26;
    }
</style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" disabled>
    <div class="keys">
        <button class="clear" onclick="clearDisplay()">C</button>
        <br><button onclick="addToDisplay('7')">7</button>
        <button onclick="addToDisplay('8')">8</button>
        <button onclick="addToDisplay('9')">9</button>
        <button onclick="addToDisplay('/')">/</button>
        <br><button onclick="addToDisplay('4')">4</button>
        <button onclick="addToDisplay('5')">5</button>
        <button onclick="addToDisplay('6')">6</button>
        <button onclick="addToDisplay('*')">*</button>
        <button onclick="addToDisplay('1')">1</button>
        <button onclick="addToDisplay('2')">2</button>
        <button onclick="addToDisplay('3')">3</button>
        <button onclick="addToDisplay('-')">-</button>
        <button onclick="addToDisplay('0')">0</button>
        <button onclick="addToDisplay('.')">.</button>
        <button onclick="calculate()">=</button>
        <button class="operator" onclick="addToDisplay('+')">+</button>
    </div>
</div>

<script>
    function addToDisplay(value) {
        document.getElementById('display').value += value;
    }

    function clearDisplay() {
        document.getElementById('display').value = '';
    }

    function calculate() {
        let display = document.getElementById('display');
        try {
            display.value = eval(display.value);
        } catch(e) {
            display.value = 'Error';
        }
    }
</script>

</body>
</html>

