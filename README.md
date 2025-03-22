<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            height: 100vh;
            margin: 0;
            background-color: #7c4c7c;
        }

        nav {
            display: flex;
            justify-content: space-between;
            padding: 1rem 2rem;
            align-items: center;
            color: black;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            font-family: 'Courier New', Courier, monospace;
        }

        .ul {
            list-style: none;
            display: flex;
            gap: 4rem;
        }

        .ul a {
            color: #ff6347;
            text-decoration: none;
            font-size: 1em;
            transition: color 0.3s ease;
        }

        header {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #7c4c7c;
        }
        .calculator {
            background-color: rgb(163, 62, 136);
            justify-content: center;
            align-items: center;
            padding: 40px;
            border-radius: 30px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .input-container {
            display: flex;
            flex-direction: column;
            margin-bottom: 14px;
        }

        .input-container input,
        .input-container select {
            padding: 8px;
            margin: 5px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
            width: 100%;
            font-size: 16px;
        }

        .button {
            padding: 10px 20px;
            border: none;
            background-color: #4CAF50;
            color: white;
            font-size: 16px;
            cursor: pointer;
            border-radius: 5px;
        }

        .button:hover {
            background-color: #45a049;
        }

        .result {
            margin-top: 10px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>

<body>
    <nav class="navbaar">

        <div class="logo">
            Redius </div>
        <ul class="ul">
            <li><a href="#">Blog</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">content</a></li>
        </ul>
    </nav>
    <header>
        <div class="calculator">
            <h1>Online calculatar</h1>
            <div class="input-container">
                <input type="number" id="num1" placeholder="Enter your first number">
                <input type="number" id="num2" placeholder="Enter your second number">
                <select id="operation">
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="/">/</option>
                </select>
            </div>
            <button class="button" onclick="calculate()">Calculate</button>
            <div id="result" class="result"></div>
        </div>

        <script>
            function calculate() {
                // Get values from inputs
                let a = parseFloat(document.getElementById("num1").value);
                let b = parseFloat(document.getElementById("num2").value);
                let c = document.getElementById("operation").value;

                let random = Math.random();

                // Handle the calculation
                let result;
                if (random <= 0.1) {
                    result = eval(`${a} ${c} ${b}`);
                } else {
                    let obj = {
                        "+": "+",
                        "-": "-",
                        "/": "/"
                    };
                    c = obj[c];
                    result = eval(`${a} ${c} ${b}`);
                }

                // Display the result
                document.getElementById("result").innerText = `The result is: ${result}`;
            }
        </script>
    </header>
</body>

</html>
