<template>
  <div class="card">
    <slot></slot>
  </div>
</template>

<style scoped>
.card {
  position: relative;
  box-shadow: 1px 0px 10px 2px rgb(128, 128, 128, 0.2);
  border-radius: 1rem;
  padding: 2rem;
  margin-bottom: 1rem;
  max-width: 40rem;
}
</style>
