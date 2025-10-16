# 🌤️ Weather Dashboard - React Application

A modern, interactive weather application built with React and JavaScript that provides real-time weather information and 7-day forecasts with an elegant, responsive user interface.

<img width="626" height="882" alt="Screenshot 2025-10-16 013454" src="https://github.com/user-attachments/assets/446af318-91a6-4eb7-bebd-9bbd0aa62a4b" />
<img width="1216" height="595" alt="Screenshot 2025-10-16 013735" src="https://github.com/user-attachments/assets/c1b93a82-5592-4021-8b57-b0820e99d2f1" />

## ✨ Features

### 🎯 Core Functionality
- **Real-time Weather Data** - Live weather information powered by Open-Meteo API
- **7-Day Weather Forecast** - Detailed predictions for the upcoming week
- **Auto-Geolocation** - Automatic location detection using browser's Geolocation API
- **City Search** - Global city search with intelligent geocoding
- **Saved Locations** - Quick access to favorite cities
- **Responsive Design** - Optimized for all devices (mobile, tablet, desktop)

### 🎨 Interactive User Experience
- **Dynamic Backgrounds** - Colors adapt to weather conditions (sunny, rainy, cloudy, snowy)
- **Animated Weather Icons** - Smooth animations for visual appeal
- **Hover Effects** - Interactive cards with scale transitions
- **Real-time Updates** - Timestamp tracking with manual refresh
- **Smooth Transitions** - Fluid animations throughout the interface
- **Temperature Scaling** - Visual feedback on hover

### 📊 Weather Information

#### Current Weather Display
- 🌡️ Current temperature with "feels like" reading
- ☁️ Weather condition descriptions
- 💧 Humidity percentage
- 💨 Wind speed (km/h)
- 📊 Atmospheric pressure (hPa)
- 👁️ Visibility range (km)

#### 7-Day Forecast
- 📅 Daily maximum and minimum temperatures
- ☀️ Weather conditions for each day
- 📆 Day names and formatted dates
- 🎨 Condition-specific weather icons
- 📱 Responsive grid layout (1-4 columns)

## 🚀 Getting Started

### Prerequisites
```bash
Node.js (v14 or higher)
npm or yarn package manager
Modern web browser with geolocation support
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/weather-dashboard.git
cd weather-dashboard
```

2. **Install dependencies**
```bash
npm install
# or
yarn install
```

3. **Start the development server**
```bash
npm start
# or
yarn start
```

4. **Open your browser**
```
Navigate to http://localhost:3000
```

### Build for Production

```bash
npm run build
# or
yarn build
```

## 🛠️ Technologies Used

### Frontend
- **React 18.x** - Component-based UI library
- **JavaScript (ES6+)** - Modern JavaScript features
- **Tailwind CSS 3.x** - Utility-first CSS framework
- **Lucide React** - Beautiful icon library

### APIs
- **Open-Meteo Weather API** - Free weather data (no API key required)
- **Geocoding API** - Location search and coordinates
- **Browser Geolocation API** - Automatic location detection

## 📦 Project Structure

```
weather-dashboard/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── components/
│   │   └── WeatherApp.jsx      # Main weather component
│   ├── App.js
│   ├── index.js
│   └── index.css
├── package.json
├── tailwind.config.js
└── README.md
```

## 🎯 How to Use

### 🔍 Search for a City
1. Type the city name in the search bar (e.g., "London", "Paris", "Tokyo")
2. Press **Enter** or click the **Search** button
3. View current weather and 7-day forecast

### 📍 Use Current Location
1. Click the **"Use My Location"** button
2. Allow location access when your browser prompts
3. Weather data for your location will load automatically

### ⭐ Save Favorite Locations
1. After viewing a location's weather, click the **star icon** next to the location name
2. Access saved locations by clicking the **star button** in the header
3. Click any saved location to load its weather instantly
4. Remove locations using the **trash icon**

### 📅 View 7-Day Forecast
- Scroll down to see the detailed forecast cards
- Each card displays:
  - Day of the week
  - Date (Month and day)
  - Weather icon
  - Condition description
  - High and low temperatures
- Hover over cards for interactive effects

### 🔄 Refresh Weather Data
- Click **"Refresh Weather"** button to get latest data
- Last updated time is shown below the location name
- Forecast updates automatically with current weather

## 🔑 API Documentation

### Open-Meteo Weather API

**Current Weather Endpoint:**
```
GET https://api.open-meteo.com/v1/forecast
```

**Parameters:**
- `latitude` - Location latitude
- `longitude` - Location longitude
- `current` - Current weather variables (temperature, humidity, wind, etc.)
- `daily` - Daily forecast variables (max/min temp, weather code)
- `timezone` - Auto timezone detection

**Documentation:** [Open-Meteo API Docs](https://open-meteo.com/en/docs)

### Geocoding API

**Search Endpoint:**
```
GET https://geocoding-api.open-meteo.com/v1/search
```

**Parameters:**
- `name` - City name to search
- `count` - Number of results (default: 1)
- `language` - Response language (default: en)

**Documentation:** [Geocoding API Docs](https://open-meteo.com/en/docs/geocoding-api)

## 🎨 Customization

### Change Weather Icons

Edit the `getWeatherIcon` or `getForecastIcon` functions in `WeatherApp.jsx`:

```javascript
const getWeatherIcon = (condition, size = 'w-24 h-24') => {
  const lower = condition.toLowerCase();
  // Add your custom icon logic
  if (lower.includes('rain')) return <CloudRain className={size} />;
  // ... more conditions
};
```

### Modify Background Colors

Update the `getBackgroundGradient` function:

```javascript
const getBackgroundGradient = (condition) => {
  const lower = condition.toLowerCase();
  if (lower.includes('rain')) return 'from-gray-600 via-gray-700 to-gray-800';
  // Add your custom gradients
};
```

### Add More Weather Details

1. Extend the API call with additional parameters
2. Update the weather state object
3. Add new display cards in the grid layout

### Customize Forecast Days

```javascript
// Change number of forecast days (max 16 available from API)
const forecastData = data.daily.time.slice(1, 8); // Shows 7 days
// Change to .slice(1, 11) for 10 days
```

## 🌐 Browser Support

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | Latest | ✅ Fully Supported |
| Firefox | Latest | ✅ Fully Supported |
| Safari | Latest | ✅ Fully Supported |
| Edge | Latest | ✅ Fully Supported |
| Opera | Latest | ✅ Fully Supported |

**Note:** Geolocation requires HTTPS or localhost environment.

## 📱 Responsive Breakpoints

| Device Type | Screen Size | Forecast Layout |
|-------------|-------------|-----------------|
| 📱 Mobile | 320px - 767px | 1 column |
| 📱 Tablet | 768px - 1023px | 2 columns |
| 💻 Desktop | 1024px - 1279px | 3 columns |
| 🖥️ Large Screen | 1280px+ | 4 columns |

## 🔒 Privacy & Security

- ✅ No user data collection or storage on external servers
- ✅ Location data used only for weather lookup
- ✅ Saved locations stored in browser memory (session-based)
- ✅ No authentication or personal information required
- ✅ Direct API calls to public endpoints only
- ✅ No cookies or user tracking
- ✅ No third-party analytics

## 🚧 Future Enhancements

### Completed Features
- [x] 7-day weather forecast ✅
- [x] Auto-geolocation ✅
- [x] City search functionality ✅
- [x] Saved locations ✅

### Planned Features
- [ ] Hourly weather breakdown (24-hour forecast)
- [ ] Weather alerts and severe weather notifications
- [ ] Unit conversion (Celsius ↔ Fahrenheit, km/h ↔ mph)
- [ ] Multiple language support (i18n)
- [ ] Dark/Light theme toggle with system preference
- [ ] Weather maps integration (radar, satellite)
- [ ] Historical weather data and trends
- [ ] Air Quality Index (AQI) display
- [ ] UV Index and sun protection recommendations
- [ ] Sunrise/sunset times with visual indicators
- [ ] Moon phases calendar
- [ ] Precipitation probability charts
- [ ] Wind direction compass
- [ ] Export weather data (CSV, PDF)
- [ ] Weather widgets for embedding
- [ ] Progressive Web App (PWA) support
- [ ] Offline mode with cached data
- [ ] Voice search integration
- [ ] Weather comparison between cities

