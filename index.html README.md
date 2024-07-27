<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weather App</title>
    {% load static %}
    <link rel="stylesheet" type="text/css" href="{% static 'weather/css/main.css' %}">
    
</head>

<body>
    <h1>Weather App</h1>
    <form method="post" action="">
        {% csrf_token %}
        <input type="text" name="city" placeholder="Enter city name">
        <button type="submit">Get Weather</button>
    </form>
    {% if weather %}
        <div>
            <div class="container">
                <h2>Weather in {{ weather.city }}</h2>
                <p>Temperature: {{ weather.temperature }}°C</p>
                <p>Description: {{ weather.description }}</p>
                <p>Wind Speed: {{ weather.wind_speed }} m/s</p>
                <p>Humidity: {{ weather.humidity }}%</p>
                <img src="http://openweathermap.org/img/wn/{{ weather.icon }}@2x.png" alt="Weather icon">
            </div>
        </div>
    {% endif %}
</body>
</html>
