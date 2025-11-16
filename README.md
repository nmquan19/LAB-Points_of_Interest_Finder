# Vietnam Points of Interest Finder

A web application that allows users to search for locations in Vietnam and displays 5 points of interest on an interactive map using OpenStreetMap API.

## Features

- 🔍 Search for any location in Vietnam
- 🗺️ Interactive map display using Leaflet.js and OpenStreetMap
- 📍 Shows 5 points of interest near the searched location
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

## Installation

1. Install dependencies:
```bash
npm install
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
4. Click on markers to see more details about each location
5. Scroll down to see a detailed list of all points of interest

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
- `radius` (optional): Search radius in meters (default: 2000)

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
├── public/
│   ├── index.html      # Main HTML file
│   └── app.js          # Frontend JavaScript
├── server.js           # Express server
├── package.json        # Dependencies
└── README.md          # This file
```

## Notes

- The application uses OpenStreetMap's free APIs with rate limiting
- Please be respectful of API usage limits
- Results may vary based on available data in OpenStreetMap
- The application is configured to search specifically within Vietnam

## Future Enhancements

- Add filters for different types of POIs (restaurants, museums, etc.)
- Save favorite locations
- Add directions between points
- Export POI list
- Multi-language support

## License

ISC
