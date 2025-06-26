# stock-price-predictor  
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Stock Price Predictor</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <style>
        body {
            background-color: #f7f9fc;
            font-family: 'Segoe UI', sans-serif;
        }
        .container {
            max-width: 600px;
            margin-top: 80px;
        }
        .result {
            margin-top: 30px;
        }
    </style>
</head>
<body>
    <div class="container text-center shadow p-4 bg-white rounded">
        <h2 class="mb-4 text-primary">📈 Stock Price Predictor</h2>
        <form method="POST" action="/predict">
            <div class="mb-3">
                <label for="symbol" class="form-label">Enter Stock Symbol (e.g., AAPL):</label>
                <input type="text" id="symbol" name="symbol" class="form-control" required>
            </div>
            <div class="mb-3">
                <label for="days" class="form-label">Days to Predict:</label>
                <input type="number" id="days" name="days" class="form-control" value="30" min="1" required>
            </div>
            <button type="submit" class="btn btn-primary w-100">Predict</button>
        </form>
        <div class="result">
            <!-- You can inject prediction results here from Flask -->
            {% if prediction %}
            <h4 class="text-success mt-4">Prediction completed. Check the graph below!</h4>
            <img src="{{ url_for('static', filename='plot.png') }}" class="img-fluid mt-3"/>
            {% endif %}
        </div>
    </div>
</body>
</html>
