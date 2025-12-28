# Weather API CLI (Java)

A simple **Java CLI application** that fetches **real-time weather data** for a given city using the **Open-Meteo API**.  
The program resolves the city name to geographic coordinates and then displays current weather conditions directly in the terminal.

## Features

- City name → latitude/longitude via Open-Meteo Geocoding API
- Current weather data:
  - Temperature (°C)
  - Relative humidity (%)
  - Wind speed (km/h)
- Simple interactive CLI loop
- No API key required
- Lightweight JSON parsing

## APIs Used

- **Geocoding API**  
  `https://geocoding-api.open-meteo.com/v1/search`

- **Weather Forecast API**  
  `https://api.open-meteo.com/v1/forecast`

## Tech Stack

- Java
- `HttpURLConnection`
- `json-simple`
- Open-Meteo public APIs


The main logic lives in `WeatherAPIData.java` 
## How It Works

1. User enters a city name.
2. The app queries the geocoding API to get latitude and longitude.
3. Coordinates are used to request current weather data.
4. Weather information is printed to the console.
5. Repeat until the user types `no`.

## Running the Project

### Requirements

- Java 8 or higher
- `json-simple` library available on the classpath

### Compile and Run

```bash
mvn clean compile
mvn exec:java
```

### Example Output

=========================
Enter the city, "no" for quit:
London
Time: 2025-01-02T14:00
Temperature: 12.4
Humidity: 78
Wind speed: 15.2

### Notes
    If a city is not found, the API may return no results.
    Network errors are printed directly to the console.
    Spaces in city names are handled automatically.

### Possible Improvements
    Better error handling for missing cities
    Unit selection (°C / °F)
    Forecast for multiple days
    Refactor into service classes
    Convert to a REST API or Spring Boot project
