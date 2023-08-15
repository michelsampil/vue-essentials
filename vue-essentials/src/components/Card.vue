<script>

</script>

<template>
  <div class="card">
    <span></span>
    <slot class="content"></slot>
  </div>
</template>

<style scoped>
.card {
  position: relative;
  width: 190px;
  height: 254px;
  color: #fff;
  transition: 0.5s;
  cursor: pointer;
}

.card:hover {
  color: #8F00FF;
  transition: 1.5s;
}
</style>