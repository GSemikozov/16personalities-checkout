<template>
  <div :class="$style.container">
    <slot />
  </div>
</template>

<style module lang="less">
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 10px;
}
</style>

<script>
export default {
  name: 'Container'
}
</script>