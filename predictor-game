<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Predictor Game</title>
    <script>
        window.onload = function() {
            // Listen for messages from Wix
            window.addEventListener("message", function(event) {
                if (event.origin.includes("wixsite.com")) {
                    let userData = event.data;
                    
                    if (userData && userData.email) {
                        document.getElementById("emailInput").value = userData.email;
                        document.getElementById("loginMessage").style.display = "none";
                        document.getElementById("gameContainer").style.display = "block";
                    } else {
                        document.getElementById("loginMessage").style.display = "block";
                        document.getElementById("gameContainer").style.display = "none";
                    }
                }
            }, false);
        };
        window.onload = function() {
    window.addEventListener("message", function(event) {
        // Ensure the message is from Wix (for security)
        if (event.origin.includes("wixsite.com")) {
            let userData = event.data;
            
            if (userData && userData.email) {
                document.getElementById("emailInput").value = userData.email;
                document.getElementById("loginMessage").style.display = "none";
                document.getElementById("gameContainer").style.display = "block";
            } else {
                document.getElementById("loginMessage").style.display = "block";
                document.getElementById("gameContainer").style.display = "none";
            }
        }
    }, false);
};

        function submitPrediction() {
            let email = document.getElementById("emailInput").value;
            if (!email) {
                alert("Please log in via Wix.");
                return;
            }

            let predictionData = {
                email: email,
                prediction1: document.getElementById("prediction1").value,
                prediction2: document.getElementById("prediction2").value,
                prediction3: document.getElementById("prediction3").value,
                points: 0
            };

            console.log("Prediction saved:", predictionData);
            alert("Your predictions have been submitted!");
        }
    </script>
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
    </style>
</head>
<body>
    <div id="loginMessage" style="color: red;">Please log in via Wix.</div>
    <div class="container" id="gameContainer" style="display: none;">
        <h2>Predict the Results!</h2>
        <p>Select your predictions for this week’s matches:</p>

        <div class="match">
            <p>Manchester United vs Liverpool</p>
            <select id="prediction1">
                <option value="1">Man Utd Win</option>
                <option value="X">Draw</option>
                <option value="2">Liverpool Win</option>
            </select>
        </div>

        <div class="match">
            <p>Real Madrid vs Barcelona</p>
            <select id="prediction2">
                <option value="1">Real Madrid Win</option>
                <option value="X">Draw</option>
                <option value="2">Barcelona Win</option>
            </select>
        </div>

        <div class="match">
            <p>Bayern Munich vs Borussia Dortmund</p>
            <select id="prediction3">
                <option value="1">Bayern Win</option>
                <option value="X">Draw</option>
                <option value="2">Dortmund Win</option>
            </select>
        </div>

        <input type="email" id="emailInput" placeholder="Your Email" readonly>
        <button onclick="submitPrediction()">Submit Predictions</button>
    </div>
</body>
</html>
