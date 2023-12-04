<template>
  <div id="app" :class="typeof weather.main != 'undefined'&&weather.main.temp > 16 ? 'warm' : '' ">
  
      

    <main>
      <div class="search-box">
        <input type="type" class="search-bar" placeholder="Search..." v-model="query" @keypress="fetchWeather" />
      </div>

      <div class="weather-wrap" v-if="typeof weather.main != 'undefined'">
        <div class="location-box">
          <div class="location">{{ weather.name }}, {{weather.sys.country}} </div>
          <div class="date">{{ dateBuilder()}}</div>
        </div>
        <div class="weather-box">
          <div class="temp">{{Math.round(weather.main.temp)}}°C</div>
          <div class="weather">{{weather.weather[0].main}}</div>
        </div>
      </div>
    </main>
    <div class="mini-footer">
      <p>
        Images by wirestock on Freepik:
        <a href="https://www.freepik.com/free-photo/aerial-view-mountain-covered-fog-beautiful-pink-sky_8281325.htm#query=mountain%20background&position=13&from_view=search&track=ais&uuid=d5a61cf7-ab85-4fcb-bb01-820beda8d57b">warm</a>,
        <a href="https://www.freepik.com/free-photo/beautiful-shot-high-white-hilltops-mountains-covered-fog_7629796.htm#query=mountain%20background&position=6&from_view=search&track=ais&uuid=d5a61cf7-ab85-4fcb-bb01-820beda8d57b">cold</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      
      api_key: '41722953812dbf29ed7a6f7b7ab984af',
    url_base: 'https://api.openweathermap.org/data/2.5/',
  query: '',
  weather: {} 
  };
  }, 
  methods: {
    fetchWeather (e) {
      if (e.key == 'Enter') {
        fetch(`${this.url_base}weather?q=${this.query}&units=metric&APPID=${this.api_key}`)
        .then (res => {
          return res.json();
        }).then(this.setResults);
      }
    },
    setResults(results) {
      this.weather = results; 
    },
    dateBuilder () {
      let d = new Date () ; 
      let months = ["January", "February", "March", "April", "May", "June",
    "July", "August", "September", "October", "November", "December"];
      let days = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"]; 

      let day = days [d.getDay()]; 
      let date = d.getDate(); 
      let month = months [d.getMonth()];  
      let year = d.getFullYear(); 
      return `${day} ${date} ${month} ${year}`
    }
  }
};
</script>

<style>
*{
  margin:0;
  padding:0;
  box-sizing: border-box;
}
body{
font-family: 'monserrat', sans-serif;
}
#app{
  background-image: url(./assets/cold-bg.jpg);
  background-size: cover;
  background-position: bottom;
  transition: 0.4s; 
}

#app.warm{
  background-image: url(./assets/warm-bg.jpg);
  background-size: cover;
  background-position: bottom;
  transition: 0.4s; 
}

main {
  min-height: 100vh; 
  padding:25px;
  background-image: linear-gradient(to bottom, rgba(0,0,0,0.25), rgba(0,0,0,0.75));
}
.search-box {
  width: 100%;
  margin-bottom: 30px;
}

.search-box .search-bar {
  display: block;
  width: 100%;
  padding: 15px;
  color: #313131;
  font-size: 20px;
  appearance: none;
  border: none;
  outline: none;
  background: none;

  box-shadow: 0px 0px 8px rgba(0,0,0,0.25);
background-color: rgba(255, 255, 255, 0.5);
border-radius: 0px 16px 0px 16px ;
transition: 0.4s;
}

.search-box .search-bar:focus {
  box-shadow: 0px 0px 16px rgba(0,0,0,0.25);
  background-color:  rgba(255, 255, 255, 0.75);
  border-radius: 16px 0px 16px 0px ;
}

.location-box .location {
  color: #FFF; 
  font-size: 32px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0,0,0,0.25);
}

.location-box .date {
  color: #FFF; 
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}

.weather-box {
  text-align: center;
}

.weather-box .temp {
  display: inline-block;
  padding: 10px 25px ;
  color: #FFF; 
  font-size: 102px;
  font-weight: 900;
  text-shadow: 3px 6px rgba(0,0,0,0.25);
  background-color:  rgba(255, 255, 255, 0.25);
  border-radius: 16px;
  margin: 30px 0px;
  box-shadow: 3px 6px rgba(0,0,0,0.25);
}

.weather-box .weather {
  color: #FFF; 
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0,0,0,0.25);
 
}

.mini-footer {
  background-color: #f0f0f0;
  padding: 10px;
  text-align: center;
  font-size: 12px;
}
</style>
