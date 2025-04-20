<!-- Daniel Stevens u18135600 -->
<template>
    <div id="contact">
    <h1>Contact Me!</h1>
        
    <form name="contact" method="POST" data-netlify="true">
        <input type="hidden" name="form-name" value="contact" />
        <label>Name: <input type="text" name="name" required /></label>
        <label>Email: <input type="email" name="email" required /></label>
        <label>Message: <textarea name="message" required></textarea></label>
        <button type="submit">Send</button>
        <input type="reset">            


    </form>        
    </div>

</template>

<style scoped>
h1{
    text-align: center;
}
form {
  max-width: 500px;
  margin: 2rem auto;
  padding: 2rem;
  background-color: #1a5738;
  border-radius: 8px;
  display: flex;
  flex-direction: column;   
  gap: 1rem;
}

label {
  display: flex;
  flex-direction: column;
  font-weight: bold;
  color: #35b776;
}

input[type="text"],
input[type="email"],
textarea {
  padding: 0.6rem;
  border: 1px solid #277851;
  background-color: #7bb599;
  border-radius: 4px;
  font-size: 1rem;
  margin-top: 0.25rem;
  font-family: inherit;
}

textarea {
  resize: vertical;
  min-height: 100px;
}

button,
input[type="reset"] {
  padding: 0.6rem 1.2rem;
  font-size: 1rem;
  border: none;
  border-radius: 4px;
}

button {
  background-color: #38ca97;
  color: white;
}

button:hover {
  background-color: #8ce1a6;
}

input[type="reset"] {
  background-color: #839f85;
  color: #333;
}

input[type="reset"]:hover {
  background-color: #d1d5db;
}
</style>