<template>
  <div class="list-container">
    <ResourceCard v-for="item in resourceList" :key="item.id" :title="item.title" :description="item.description"
      :link="item.link" />
  </div>
</template>

<script>
import ResourceCard from './ResourceCard.vue'
export default {
  props: {
    resourceList: Array
  },
  data() {
    return {
    };
  },
  components: { ResourceCard }
}
</script>

<style scoped>
.list-container {
  margin-top: 70px;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>