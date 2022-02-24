<template>
  <div class="fields">
    <div>
      <h3>Date</h3>
      <input type="text" />
    </div>
    <span>
      <h3>Time</h3>
      <input type="text" />
    </span>
  </div>
</template>

<script>
export default {
  name: "Fields",
}
</script>

<style scoped>
.fields {
  display: flex;
  justify-content: space-around;
  width: 100%;
}
</style>
