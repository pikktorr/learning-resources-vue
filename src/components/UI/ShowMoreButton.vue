<template>
  <a :href="link" target="_blank" rel="noopener noreferrer">
    <CustomButton class="show-more-button">
      SHOW MORE
    </CustomButton>
  </a>
</template>

<script>
import CustomButton from "./CustomButton.vue";
export default {
  props: {
    link: String,
  },
  components: { CustomButton }
}
</script>

<style scoped>
.show-more-button {
  padding: 6px 8px;
  border: none;
  background-color: rgba(96, 157, 159, 0.1);
}
</style>