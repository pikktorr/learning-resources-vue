<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script></script>

<style scoped>
.button {
  background: none;
  color: cadetblue;
  border: 1px solid cadetblue;
  border-radius: 2rem;
  padding: 12px 16px;
  cursor: pointer;
}

.button:hover {
  background-color: cadetblue;
  color: white;
}
</style>