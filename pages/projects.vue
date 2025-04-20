<!-- Daniel Stevens u18135600 -->
<template>
    <div id="proj-page">
        <h1>Projects</h1>
        <p>This is a small collection of the projects I have worked on.</p>
        <span class="useless-fact" v-if="fact && fact.text">Fun Fact! {{ fact.text }}</span>
        <span class="useless-fact" v-else-if="error">Couldn't load a fun fact.</span>
        <span class="useless-fact" v-else>Loading a fun fact...</span>
        <div class="projects">
            <div id="top">
                <div class="project">
                    <h2>FrankenStein Photoshop project </h2>
                    <img id="proj1" src="/images/project1.jpg" alt="Project 1">
                    <p>We had to combine 15 unique images to create a character. Mine was heavily inspired by Game of Thrones and DnD.</p>
                </div>
                <div class="project">
                    <h2>Illustrate T-Shirt</h2>
                    <img id="proj2" src="/images/project2.jpg" alt="Project 2">
                    <p>This was an adobe illustration for a project where we had to design an illustration for a t-shirt</p>
                </div>                
            </div>

            <div id="project3" class="project">
                <h2>Industrial Scale Green Energy Greenhouse </h2>
                <img id="proj3" src="/images/project3.PNG" alt="Project 3">
                <p>A project from back when I was studying mechanical engineering. We had to design an industrial scale greenhouse for a theoretical farm outside of 
                    Pretoria that could grow cucumbers, watermelon, tomatoes etc that the client would want. This design incorporated a heated waterbed design for the 
                    greenhouse using solar water heaters and a traditional donkey as a backup heating system.
                </p>
            </div>
        </div>

    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const fact = ref(null)
const error = ref(null)

onMounted(async () => {
  try {
    const res = await fetch("https://uselessfacts.jsph.pl/api/v2/facts/random?language=en", {
      headers: { Accept: "application/json" }
    })
    fact.value = await res.json()
  } catch (err) {
    error.value = err
  }
})



</script>

<style scoped>
#proj1, #proj2{
    height: 500px;
    width: 400px;
}
#proj3{
    width: 800px;
}
#proj-page{
    width: 80%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
}

#top p{
    max-width: 500px;
}

#top .project{
    width: 600px;
}

#project3 p{
    max-width: 700px;
}

#top{
    display: flex;
    justify-content: space-between;
}

.project{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

img{
    border-radius: 5px;
    box-shadow: 5px 5px 4px #000000;
}

.useless-fact{
    margin: 20px;
    max-width: 400px;
    border-radius: 10px;
    background-color: #102c1e;
    margin: 10px;
    padding: 20px;
    box-shadow: inset;
}


</style>