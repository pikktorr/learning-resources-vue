<template>
  <CardWrapper>
    <RemoveButton />
    <h1><b> {{ title }}</b></h1>
    <p>{{ description }}</p>
    <div class="buttonGroup">
      <ShowMoreButton :link="link"/>
    </div>
  </CardWrapper>
</template>

<script>
import CardWrapper from './UI/CardWrapper.vue'
import RemoveButton from './UI/RemoveButton.vue'
import ShowMoreButton from './UI/ShowMoreButton.vue'
export default {
  props: {
    title: String,
    description: String,
    link: String,
  },
  data() {
    return {};
  },
  components: { CardWrapper, RemoveButton, ShowMoreButton }
}
</script>

<style scoped>
.buttonGroup {
  display: flex;
  justify-content: flex-end;
}

h1,
p {
  margin-bottom: 1rem;
}
</style>
