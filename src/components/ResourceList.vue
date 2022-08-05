<template>
  <div class="list-container">
    <ResourceCard v-for="item in resourceList" :key="item.id" :id="item.id" :title="item.title"
      :description="item.description" :link="item.link" />
  </div>
</template>

<script>
import ResourceCard from './ResourceCard.vue'
export default {
  inject: ['resourceList'],
  data() {
    return {
    };
  },
  components: { ResourceCard }
}
</script>

<style scoped>
.list-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>