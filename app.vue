<!-- Daniel Stevens u18135600 -->
<template>
  <div id="app">
    <nav>
      <ul>
        <li><NuxtLink to="/">Home</NuxtLink></li>
        <li><NuxtLink to="/projects">Projects</NuxtLink></li>
        <li><NuxtLink to="/contact">Contact</NuxtLink></li>
      </ul>
    </nav>
    <NuxtPage/>    
  </div>

</template>

<style>
body{
  background-color:  #123524;
  color: rgb(202, 202, 202);
}
#app{
  font-family: Helvetica, sans-serif;
}

h1{
  font-family: 'Courier New', Courier, monospace;
  font-size: 3rem;
  color: rgb(202, 202, 202);

}

h2{
  color: rgb(202, 202, 202);

}

nav{
  background-color:  #277851;
  width: 100%;
  display: flex;
  height: 80px;
  justify-content: center;
}

nav ul{
  display: flex;
  align-items: center;
}

li{
  list-style-type: none;
}

a{
  text-decoration: none;
  color: #49b17d;
  border-radius: 10px;
  background-color: #102c1e;
  margin: 10px;
  padding: 20px;
  box-shadow: inset;

}

a:hover{
  color: purple;
}


</style>