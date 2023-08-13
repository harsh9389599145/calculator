<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body> 
    <div class="calculator">
        <input type="text" class="screen" id="screen" placeholder="0">
        <button class="symbol" onclick="wipe('AC')">AC</button>
        <button class="symbol" onclick="wipe('C')">C</button>
        <button class="symbol" onclick="show('/')">/</button>
        <button class="symbol" onclick="show('*')">*</button>

        <button class="number" onclick="show('7')">7</button>
        <button class="number" onclick="show('8')">8</button>
        <button class="number" onclick="show('9')">9</button>
        <button class="symbol" onclick="show('-')">-</button>
        
        
        <button class="number" onclick="show('4')">4</button>
        <button class="number" onclick="show('5')">5</button>
        <button class="number" onclick="show('6')">6</button>
        <button class="symbol" onclick="show('+')">+</button>

        
        <button class="number" onclick="show('1')">1</button>
        <button class="number" onclick="show('2')">2</button>
        <button class="number" onclick="show('3')">3</button>
        <button class="symbol" onclick="show('.')">.</button>

        
        <button class="number" onclick="show('(')">(</button>
        <button class="number" onclick="show('0')">0</button>
        <button class="number" onclick="show(')')">)</button>
        <button class="symbol" onclick="calc()">=</button>
    </div>

    <script>
        let display = document.getElementById('screen');

        const wipe = (action) => {
            if (action === 'AC') {
                display.value = '';
            } else if (action === 'C') {
                display.value = display.value.slice(0, -1);
            }
        }

        const show = (n) => {
            display.value += n;
        }

        const calc = () => {
            display.value = eval(display.value);
        }
    </script>
</body>
</html>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

*::before,
*::after {
    box-sizing: inherit;
}

html,
body {
    font-size: 16px;
    font-family: Arial, sans-serif;
    height: 100%;
}

body {
    background: #7bc4a2;
    display: flex;
    align-items: center;
    justify-content: center;
    -webkit-font-feature-smoothing: antialiased;
    -webkit-tap-highlight-color: transparent;
}

input {
    border: none;
    outline: none;
}

input:focus {
    outline: none;
    background: none;
    cursor: pointer;
}

button {
    border: none;
    outline: none;
    background: none;
}

button:focus {
    outline: none;
}

.calculator {
    background: #8097e1;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: .75rem;
    width: 325px;
    border: 1px solid #7c3d3d;
    padding: .75rem;
    border-radius: 1rem;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(50%, -50%);
}

.screen {
    grid-column: 1/5;
    border-radius: .75rem;
    font-size: 2rem;
    height: 6rem;
    color: #f87fd2;
    background:black ;
    text-align: end;
    padding: .5rem;
}

::placeholder {
    color: #76c9c9;
}

.symbol,
.number {
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    aspect-ratio: 1;
    font-size: 1.25rem;
    color: #fff;
    border-radius: 50%;
    transition: .15s ease;
}

.symbol {
    background: #5d68e2;
}

.symbol:hover {
    background: #4d55b1;
}

.number {
    background: #333849;
}

.number:hover {
    background: #333849ac;
}
