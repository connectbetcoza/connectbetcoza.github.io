<!-- Predictor Game - ConnectBET -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Predictor Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f4f4f4;
            text-align: center;
            padding: 20px;
        }
        .container {
            background: white;
            max-width: 500px;
            margin: auto;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            color: #333;
        }
        .match {
            margin: 10px 0;
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }
        button {
            background: #28a745;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }
        button:disabled {
            background: #aaa;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Predict the Results!</h2>
        <p>Select your predictions for this week’s matches:</p>

        <div class="match">
            <p>Manchester United vs Liverpool</p>
            <select>
                <option value="1">Man Utd Win</option>
                <option value="X">Draw</option>
                <option value="2">Liverpool Win</option>
            </select>
        </div>

        <div class="match">
            <p>Real Madrid vs Barcelona</p>
            <select>
                <option value="1">Real Madrid Win</option>
                <option value="X">Draw</option>
                <option value="2">Barcelona Win</option>
            </select>
        </div>

        <div class="match">
            <p>Bayern Munich vs Borussia Dortmund</p>
            <select>
                <option value="1">Bayern Win</option>
                <option value="X">Draw</option>
                <option value="2">Dortmund Win</option>
            </select>
        </div>

        <button onclick="submitPredictions()">Submit Predictions</button>
        <p id="result"></p>
    </div>

    <script>
        function submitPredictions() {
            document.getElementById("result").innerText = "Predictions Submitted!";
        }
    </script>
</body>
</html>
