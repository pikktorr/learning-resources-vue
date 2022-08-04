<template>
  <div class="remove-button">
    x
  </div>
</template>

<style scoped>
.remove-button {
  position: absolute;
  top: 10px;
  right: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 30px;
  height: 30px;
  padding-bottom: 1px;
  border-radius: 50%;
  color: salmon;
  cursor: pointer;
  font-weight: bold;
}

.remove-button:hover {
  background-color: salmon;
  color: white;
}
</style>