<script setup lang="ts">

</script>

<template>
  <div id="contact" class="contactContainer">
    <h1>Contact me</h1>
    <form class="box" onSubmit={sendEmail}>
      <input type="text" name="from_name" placeholder="Name"/>
      <input type="email" name="from_email" placeholder="Your Email"/>
      <textarea name="message" placeholder="Message"/>
      <button type="submit">Send</button>
    </form>
  </div>
</template>

<style scoped>
.contactContainer {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
  padding: 6rem 0;
}

.box {
  height: 30rem;
  width: 70%;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  background-color: white;
  border-radius: 1rem;
  padding: 1.5rem;
}

input {
  width: 100%;
  height: 3rem;
  padding: 1rem;
  border-radius: 0.5rem;
  border: 1px solid transparent;
  background: whitesmoke;
  font-size: 1.2rem;
}

textarea {
  width: 100%;
  padding: 1rem;
  border-radius: 0.5rem;
  border: 1px solid transparent;
  background-color: whitesmoke;
  font-size: 1.2rem;
  flex-grow: 1;
  resize: vertical;
}

button {
  width: 100%;
  padding: 0.5rem;
  border-radius: 0.5rem;
  border: 1px solid black;
  background-color: black;
  color: white;
  font-size: 1.2rem;
  cursor: pointer;
}

</style>
