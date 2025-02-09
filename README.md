<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Predictor Game</title>
    <script type="module">
        import wixUsers from 'wix-users';
        import wixData from 'wix-data';

        $w.onReady(() => {
            let user = wixUsers.currentUser;
    
            if (!user.loggedIn) {
                $w("#loginMessage").show();
                $w("#gameContainer").hide(); // Hide the game if not logged in
            } else {
                $w("#loginMessage").hide();
                $w("#gameContainer").show();
    
                // Auto-fill email if user is logged in
                user.getEmail().then((email) => {
                    $w("#emailInput").value = email;
                });
            }
        });
    
        $w("#submitButton").onClick(() => {
            let user = wixUsers.currentUser;
            let userId = user.id;
            let email;
    
            user.getEmail()
                .then((userEmail) => {
                    email = userEmail;
    
                    // Save the user's prediction in the database
                    let predictionData = {
                        "userId": userId,
                        "email": email,
                        "prediction1": $w("#prediction1").value,
                        "prediction2": $w("#prediction2").value,
                        "prediction3": $w("#prediction3").value,
                        "points": 0  // You will update points manually
                    };
    
                    wixData.insert("PredictorGamesPredictions", predictionData)
                        .then(() => {
                            console.log("Prediction saved successfully");
                        })
                        .catch((err) => {
                            console.error("Error saving prediction:", err);
                        });
                })
                .catch((error) => {
                    console.error("Error fetching user email:", error);
                });
        });
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
        button:disabled {
            background: #aaa;
        }
    </style>
</head>
<body>
    <div id="loginMessage" style="display: none; color: red;">Please log in to make predictions.</div>
    <div class="container" id="gameContainer" style="display: none;">
        <h2>Predict the Results!</h2>
        <p>Select your predictions for this week’s matches:</p>

        <div class="match">
            <p>Chiefs vs Pirates</p>
            <select id="prediction1">
                <option value="1">Chiefs Win</option>
                <option value="X">Draw</option>
                <option value="2">Pirates Win</option>
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
        <button id="submitButton">Submit Predictions</button>
        <p id="result"></p>
    </div>
</body>
</html>
