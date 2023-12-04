# Vue Weather App

📗 Table of Contents

📖 [About the Project](#about-the-project)  
🛠 [Built With](#built-with)  
🚀 [Live Demo](#live-demo)  
💻 [Getting Started](#getting-started)  
👥 [Authors](#authors)  

## 📖 About the Project

The Vue Weather App is a client-side application that provides real-time weather information based on user searches for cities. It utilizes the OpenWeatherMap API to fetch weather data, and the application dynamically adjusts its interface, including background images, based on the temperature.

### Essential Features

**Search View:**
  - Allows users to search for cities or countries.
  - Displays weather information, including temperature.
  - Dynamically changes background images based on the temperature.

### User Stories

- As a user, I want to access real-time weather information for cities or countries.
- As a user, I want the interface to reflect the temperature visually.
- As a user, I want a simple and intuitive way to search for weather information.

## 🛠 Built With

### Technologies

- Vue.js: A progressive JavaScript framework for building user interfaces.
- OpenWeatherMap API: Provides real-time weather data.
  
### Dependencies
- @vue/cli-service
  
### Project Structure
- **src/:** Contains the source code for the Vue Weather App, stores static assets.
- **dist/:** Contains build files.

🚀 Live Demo
Live Demo Link: [https://andreawork-hub.github.io/vue-weather-app/] 

💻 Getting Started

To get a local copy up and running, follow these simple steps:
1. Clone the repository.
2. Install dependencies using npm install.
3. Lints and fixe the files npm run lint.
4. Run the development server using npm run serve.
5. Customize configuration: See [Configuration Reference](https://cli.vuejs.org/config/) 
  - vue.config.js modul export config. including the name of the repository //   publicPath: process.env.NODE_ENV === 'production' ? '/vue-weather-app/' : '/'
6. Build the project running npm run build.
7.You can deploy this project using GitHub Pages, Netlify, Vercel. 
For GitHub Pages: 
npm run build
git add dist -f // override .gitignore dist, adds only dist to gh-pages
git commit -m "adding dist"
git subtree push --prefix dist origin gh-pages  

👥 Authors
👤 Andrea V.

GitHub: @andreawork-hub



