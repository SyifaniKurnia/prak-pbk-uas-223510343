<template>
  <div class="weather-app">
    <q-card class="weather-card q-pa-md">
      <h5 align="center">Cuaca</h5>
      <div class="input-button-wrapper">
        <q-input
          v-model="location"
          placeholder="Masukkan Lokasi"
          outlined
          dense
          class="input-field"
        />
        <q-btn @click="getWeather" color="primary" class="get-weather-button">
          Dapatkan Cuaca
        </q-btn>
      </div>

      <q-card v-if="weather" class="weather-info q-mt-md">
        <q-card-section>
          <q-card-title class="weather-title"
            >Cuaca di {{ weather.name }}:</q-card-title
          >
          <p class="weather-data">
            Suhu: {{ (weather.main.temp - 273.15).toFixed(2) }} °C
          </p>
          <p class="weather-data">
            Deskripsi: {{ weather.weather[0].description }}
          </p>
          <p class="weather-data">Kelembapan: {{ weather.main.humidity }}%</p>
          <p class="weather-data">Tekanan: {{ weather.main.pressure }} hPa</p>
          <p class="weather-data">
            Kecepatan Angin: {{ weather.wind.speed }} m/s
          </p>
        </q-card-section>
      </q-card>
    </q-card>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Weather",
  data() {
    return {
      location: "",
      weather: null,
    };
  },
  methods: {
    async getWeather() {
      const apiKey = "dd256840354442bed526bb3f2bbf43b7";
      const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=${this.location}&appid=${apiKey}`;

      try {
        const response = await axios.get(apiUrl);
        this.weather = response.data;
      } catch (error) {
        console.error("Error fetching weather data:", error);
      }
    },
  },
};
</script>

<style scoped>
.weather-app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-image: url(../../public/sky.jpg);
  background-size: cover;
}

.weather-card {
  bottom: 10rem;
  max-width: 400px;
  width: 100%;
  background-color: #f0f0f0;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.input-button-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.input-field,
.get-weather-button {
  width: 100%;
}

.button-wrapper {
  margin-top: 10px;
  text-align: center;
}

.get-weather-button {
  width: 100%;
}

.weather-info {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin-top: 16px;
}

.weather-title {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 12px;
}

.weather-data {
  margin-bottom: 8px;
}
</style>
