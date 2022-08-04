<template>
  <a :href="link" target="_blank" rel="noopener noreferrer">
    <button class="show-more-button">
      SHOW MORE
    </button>
  </a>
</template>

<script>
export default {
  props: {
    link: String,
  },
}
</script>

<style scoped>
.show-more-button {
  background: none;
  color: cadetblue;
  border: 1px solid cadetblue;
  border-radius: 2rem;
  padding: 8px 10px;
  cursor: pointer;
}

.show-more-button:hover {
  background-color: cadetblue;
  color: white;
}
</style>