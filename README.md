# hw37
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Circle Properties Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f4f4f9;
        }
        .container {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            max-width: 400px;
        }
        input, button {
            padding: 8px;
            margin-top: 10px;
            font-size: 16px;
        }
        button {
            cursor: pointer;
            background-color: #0056b3;
            color: white;
            border: none;
            border-radius: 4px;
        }
        button:hover {
            background-color: #004494;
        }
        .output {
            margin-top: 20px;
            font-weight: bold;
            line-height: 1.6;
        }
    </style>
</head>
<body>

    <div class="container">
        <h2>Circle Calculator</h2>
        
        <label for="radius">Enter a radius: </label>
        <input type="number" id="radius" placeholder="e.g., 5" min="0">
        <button onclick="demonstrateFunctions()">Calculate</button>

        <div id="results" class="output"></div>
    </div>

    <script>
        // 1. Create a function called calcCircumfrence
        // Note: Used the exact spelling from your assignment prompt
        function calcCircumfrence(radius) {
            let circumference = 2 * Math.PI * radius;
            let resultText = "The circumference is " + circumference.toFixed(2);
            
            console.log(resultText); // Logs to browser console
            return resultText;       // Returns for DOM display
        }

        // 2. Create a function called calcArea
        function calcArea(radius) {
            let area = Math.PI * radius * radius;
            let resultText = "The area is " + area.toFixed(2);
            
            console.log(resultText); // Logs to browser console
            return resultText;       // Returns for DOM display
        }

        // Wrapper function to trigger the calculations and update the web page
        function demonstrateFunctions() {
            let radiusInput = parseFloat(document.getElementById("radius").value);
            let displayDiv = document.getElementById("results");

            if (isNaN(radiusInput) || radiusInput <= 0) {
                displayDiv.innerHTML = "Please enter a valid positive number.";
                return;
            }

            // Pass the radius to the functions
            let circResult = calcCircumfrence(radiusInput);
            let areaResult = calcArea(radiusInput);

            // Output the results to the web page
            displayDiv.innerHTML = circResult + "<br>" + areaResult;
        }
    </script>

</body>
</html>
