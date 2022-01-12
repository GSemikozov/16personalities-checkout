<template>
  <div :class="$style.layout">
    <slot />
  </div>
</template>

<style module lang="less">
  .layout {
    display: grid;
    grid-template-rows: auto 1fr auto;
  }
</style>

<script>
export default {
  name: 'Layout'
}
</script>