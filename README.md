<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Calculator</title>

<style>
body{
    background:#eaeaea;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    font-family:Arial;
}

.calculator{
    background:#222;
    padding:15px;
    width:260px;
    border-radius:10px;
}

#display{
    background:#cfded6;
    height:45px;
    font-size:22px;
    text-align:right;
    padding:8px;
    border-radius:5px;
    margin-bottom:10px;
}

.buttons{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:8px;
}

button{
    height:45px;
    font-size:16px;
    border:none;
    border-radius:5px;
    cursor:pointer;
}

.num{ background:#444; color:white; }
.op{ background:#777; color:white; }
.equal{ background:green; color:white; }
.clear{ background:purple; color:white; }

.zero{ grid-column:span 2; }
</style>
</head>

<body>

<div class="calculator">
    <input type="text" id="display" value="" readonly>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">AC</button>
        <button class="op" onclick="appendValue('%')">%</button>
        <button class="op" onclick="appendValue('/')">÷</button>
        <button class="op" onclick="appendValue('*')">×</button>

        <button class="num" onclick="appendValue('7')">7</button>
        <button class="num" onclick="appendValue('8')">8</button>
        <button class="num" onclick="appendValue('9')">9</button>
        <button class="op" onclick="appendValue('-')">−</button>

        <button class="num" onclick="appendValue('4')">4</button>
        <button class="num" onclick="appendValue('5')">5</button>
        <button class="num" onclick="appendValue('6')">6</button>
        <button class="op" onclick="appendValue('+')">+</button>

        <button class="num" onclick="appendValue('1')">1</button>
        <button class="num" onclick="appendValue('2')">2</button>
        <button class="num" onclick="appendValue('3')">3</button>
        <button class="equal" onclick="calculate()">=</button>

        <button class="num zero" onclick="appendValue('0')">0</button>
        <button class="num" onclick="appendValue('.')">.</button>
    </div>
</div>

<script>
let display = document.getElementById("display");

function appendValue(val){
    display.value += val;
}

function clearDisplay(){
    display.value = "";
}

function calculate(){
    try{
        display.value = eval(display.value);
    }catch{
        display.value = "Error";
    }
}
</script>

</body>
</html>
