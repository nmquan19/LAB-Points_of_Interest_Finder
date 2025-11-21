# Vietnam Points of Interest Finder

A web application that allows users to search for locations in Vietnam and displays 5 points of interest on an interactive map using OpenStreetMap API, along with real-time weather information.

## Features

- 🔍 Search for any location in Vietnam
- 🗺️ Interactive map display using Leaflet.js and OpenStreetMap
- 📍 Shows 5 points of interest near the searched location
- ☀️ Real-time weather information using OpenWeatherMap API
- 🎨 Beautiful UI with Tailwind CSS
- 📱 Responsive design for mobile and desktop

## Technologies Used

### Frontend
- **HTML5**: Structure
- **Tailwind CSS**: Styling and responsive design
- **Leaflet.js**: Interactive map visualization

### Backend
- **Node.js**: Runtime environment
- **Express.js**: Web server framework
- **Axios**: HTTP client for API requests

### APIs
- **OpenStreetMap Nominatim API**: Location geocoding
- **Overpass API**: Points of interest data
- **OpenWeatherMap API**: Real-time weather information

## Installation

1. Install dependencies:
```bash
npm install
```

2. Configure the Weather API:
   - Open `config.js` in the root directory
   - Replace the placeholder API key with your OpenWeatherMap API key
   - Get a free API key at [OpenWeatherMap](https://openweathermap.org/api)

```javascript
const config = {
    WEATHER_API_KEY: 'YOUR_API_KEY_HERE'
}
```

## Running the Application

1. Start the server:
```bash
npm start
```

Or for development with auto-reload:
```bash
npm run dev
```

2. Open your browser and navigate to:
```
http://localhost:3000
```

## Usage

1. Enter a location name in Vietnam (e.g., "Hanoi", "Ho Chi Minh City", "Da Nang")
2. Click the "Search" button or press Enter
3. View the location and 5 points of interest on the map
4. Check the real-time weather information for the selected location
5. Click on markers to see more details about each location
6. Scroll down to see a detailed list of all points of interest with icons and coordinates

## API Endpoints

### GET `/api/search-location`
Search for a location in Vietnam.

**Query Parameters:**
- `location` (required): Name of the location in Vietnam

**Response:**
```json
{
  "name": "Hanoi, Vietnam",
  "lat": 21.0285,
  "lon": 105.8542,
  "boundingbox": [...]
}
```

### GET `/api/points-of-interest`
Get points of interest near a location.

**Query Parameters:**
- `lat` (required): Latitude
- `lon` (required): Longitude
- `radius` (optional): Search radius in meters (default: 2000, frontend uses 5000)

**Response:**
```json
{
  "pois": [
    {
      "id": 123456,
      "name": "Hoan Kiem Lake",
      "type": "attraction",
      "lat": 21.0285,
      "lon": 105.8542,
      "tags": {...}
    }
  ]
}
```

## Project Structure

```
├── index.html          # Main HTML file
├── app.js              # Frontend JavaScript (map & weather)
├── config.js           # Configuration (Weather API key)
├── server.js           # Express server with API endpoints
├── package.json        # Dependencies and scripts
└── README.md           # This file
```

## Weather Information

The application displays comprehensive weather data including:
- Current temperature and "feels like" temperature
- Weather description with animated icons
- Humidity percentage
- Wind speed (m/s)
- Atmospheric pressure (hPa)
- Visibility (km)

Weather data is automatically fetched when you search for a location.

## Notes

- The application uses OpenStreetMap's free APIs with rate limiting
- Weather data requires an OpenWeatherMap API key (configured in `config.js`)
- Please be respectful of API usage limits
- Results may vary based on available data in OpenStreetMap
- The application is configured to search specifically within Vietnam
- Weather information updates with each location search

## Dependencies

- **express** (^4.18.2): Web server framework
- **axios** (^1.6.0): HTTP client for API requests
- **cors** (^2.8.5): Enable CORS for API endpoints
- **nodemon** (^3.0.1): Development auto-reload (dev dependency)

## Future Enhancements

- Add filters for different types of POIs (restaurants, museums, etc.)
- Save favorite locations
- Add directions between points
- Weather forecast (multi-day predictions)
- Export POI list
- Multi-language support
- Historical weather data

## License

ISC
