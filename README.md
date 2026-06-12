<!DOCTYPE html>
<html>
<head>
    <title>Beautiful Calculator</title>

    <style>
        *{
            margin:0;
            padding:0;
            box-sizing:border-box;
            font-family:Arial, sans-serif;
        }

        body{
            height:100vh;
            display:flex;
            justify-content:center;
            align-items:center;
            background:linear-gradient(135deg,#667eea,#764ba2);
        }

        .calculator{
            background:white;
            padding:20px;
            border-radius:20px;
            box-shadow:0 10px 25px rgba(0,0,0,0.3);
            width:320px;
        }

        #display{
            width:100%;
            height:70px;
            border:none;
            outline:none;
            text-align:right;
            font-size:30px;
            padding:10px;
            margin-bottom:15px;
            border-radius:10px;
            background:#f2f2f2;
        }

        .buttons{
            display:grid;
            grid-template-columns:repeat(4,1fr);
            gap:10px;
        }

        button{
            height:60px;
            border:none;
            border-radius:12px;
            font-size:22px;
            cursor:pointer;
            transition:0.2s;
        }

        button:hover{
            transform:scale(1.05);
        }

        .operator{
            background:#ff9500;
            color:white;
        }

        .clear{
            background:#ff3b30;
            color:white;
        }

        .equal{
            background:#34c759;
            color:white;
        }

        .number{
            background:#e5e5ea;
        }
    </style>
</head>
<body>

<div class="calculator">

    <input type="text" id="display" readonly>

    <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button class="operator" onclick="appendValue('/')">÷</button>
        <button class="operator" onclick="appendValue('*')">×</button>
        <button class="operator" onclick="appendValue('-')">−</button>

        <button class="number" onclick="appendValue('7')">7</button>
        <button class="number" onclick="appendValue('8')">8</button>
        <button class="number" onclick="appendValue('9')">9</button>
        <button class="operator" onclick="appendValue('+')">+</button>

        <button class="number" onclick="appendValue('4')">4</button>
        <button class="number" onclick="appendValue('5')">5</button>
        <button class="number" onclick="appendValue('6')">6</button>
        <button class="equal" onclick="calculate()">=</button>

        <button class="number" onclick="appendValue('1')">1</button>
        <button class="number" onclick="appendValue('2')">2</button>
        <button class="number" onclick="appendValue('3')">3</button>
        <button class="number" onclick="appendValue('.')">.</button>

        <button class="number" onclick="appendValue('0')" style="grid-column:span 4;">
            0
        </button>
    </div>

</div>

<script>
    function appendValue(value){
        document.getElementById("display").value += value;
    }

    function clearDisplay(){
        document.getElementById("display").value = "";
    }

    function calculate(){
        try{
            document.getElementById("display").value =
            eval(document.getElementById("display").value);
        }
        catch{
            document.getElementById("display").value = "Error";
        }
    }
</script>

</body>
</html>
