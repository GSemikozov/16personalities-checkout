<template>
  <main :class="$style.main" role="main">
    <slot />
  </main>
</template>

<style module lang="less">
.main {
  padding: 20px 0;
}
</style>

<script>
export default {
  name: 'Main'
}
</script>