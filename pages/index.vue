<!-- Daniel Stevens u18135600 -->
<template>
    <div id="index">
        <h1>Daniel Thomas Stevens</h1>
        <img id="profilepic" src="/images/profile.jpg" alt="A photo of me in a hat">
        <p>
            I am a Multimedia second year student studying at the University of Pretoria. 
            I am what many would describe as a nerd. I am an avid board gamer with a sizable collection,
            I love science fiction and fantasy books with Terry Pratchett as my favourite author. Music is 
            a big part of my life as well. I play bass clarinet in the university wind band and orchestra and 
            I have an embarrassingly high number or minutes listened to on Spotify. Thunderstorms are my favourite weather.

        </p>
        <span class="weather" v-if="weather && weather.current">Speaking of. Todays weather in {{ weather.location.name }}: {{ weather.current.temperature }}°C, {{ weather.current.weather_descriptions[0] }}</span>
        <span class="weather" v-else-if="weatherError">Couldn't load a weather.</span>
        <span class="weather" v-else>Loading weather...</span>

    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const weather = ref(null)
const weatherError = ref(null)

onMounted(async () => {
  try {
    const res = await fetch("http://api.weatherstack.com/current?access_key=ad613791bc9bf2d0f25e13e412ffa876&query=Pretoria&units=m")
    weather.value = await res.json()
  } catch (err) {
    weatherError.value = err
  }
})
</script>

<style>
#profilepic{
    max-width: 200px;
    border-radius: 100%;
}

#index{
    width: 80%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
}

#index p{
    max-width: 600px;
    padding: 10px;
}

p{
    line-height: 1.5rem;
}

.weather{
    margin: 20px;
    max-width: 400px;
    border-radius: 10px;
    background-color: #102c1e;
    margin: 10px;
    padding: 20px;
    box-shadow: inset;
}

</style>