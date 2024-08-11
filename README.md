# GeoSphere

GeoSphere is a location-based web application that provides detailed information about the user's current country and its neighboring countries. The app leverages the BigDataCloud API for reverse geocoding to determine the user's location and a custom API to fetch country details, including flags, population, languages, and currencies.

## Features

- **Geolocation-Based Country Information**: Automatically fetches the user's current country based on their geolocation.
- **Neighboring Countries**: Displays information about neighboring countries of the user's current location.
- **Error Handling**: Gracefully handles errors and displays appropriate messages to the user.

## Technologies Used

- **JavaScript (ES6+)**
- **HTML/CSS**
- **BigDataCloud API**: Used for reverse geocoding to get the user's location.
- **Custom Countries API**: Fetches detailed country data, including neighboring countries.

## How It Works

1. **Geolocation**: The app first gets the user's current latitude and longitude using the `navigator.geolocation.getCurrentPosition` method.
  
2. **Reverse Geocoding**: It sends these coordinates to the BigDataCloud API to retrieve the country name.
  
3. **Fetching Country Data**: Using the country name, the app then queries a custom Countries API to get detailed information about that country, such as its flag, population, language, and currency.
  
4. **Fetching Neighboring Countries**: The app also retrieves information about neighboring countries by querying the same API using the country codes of the neighbors.

5. **Rendering**: The country data is then dynamically rendered on the webpage.

## Setup and Usage

1. Clone this repository to your local machine:
    ```bash
    git clone https://github.com/your-username/geosphere.git
    ```

2. Navigate into the project directory:
    ```bash
    cd geosphere
    ```

3. Open the `index.html` file in your browser.

4. Click the "Get Country" button to view information about your current location and its neighboring countries.

## Code Explanation

The primary logic of the application is located in the `index.js` file:

- **`getPosition`**: Returns a promise that resolves with the user's geolocation coordinates.
- **`whereAmI`**: An async function that fetches the country and neighboring country data based on the user's geolocation.
- **`renderCountry`**: Renders the country information into the DOM.
- **`renderError`**: Displays error messages in the UI.

## Error Handling

- If the geolocation retrieval or API calls fail, appropriate error messages are displayed to the user.
