<template>
  <TheHeader />
  <main class="main-container">
    <ResourceSelector />
  </main>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import ResourceSelector from './components/ResourceSelector.vue';
export default {
  data() {
    return {
    };
  },
  components: { TheHeader, ResourceSelector }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@300;400;700&family=Roboto:wght@300;400;700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Comfortaa', cursive;
}

input,
textarea {
  min-height: 30px;
  padding: 4px;
  font-family: 'Roboto';
  font-weight: 300;
  font-size: 14px;
}

h1 {
  font-weight: 700;
  text-transform: uppercase;
}

p {
  font-family: 'Roboto';
  font-weight: 300;
  font-size: 14px;
}

a {
  color: inherit;
  text-decoration: none;
}

a:visited {
  color: inherit
}

button {
  transition: 0.2s;
}

.main-container {
  padding: 2rem;
  margin: 70px auto;
  max-width: 40rem;
}
</style>