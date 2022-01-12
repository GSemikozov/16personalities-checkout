<template>
  <hr :class="$style.delimiter" />
</template>

<style module lang="less">
.delimiter {
  border: 0;
  height: 1px;
  background-color: var(--grey-5);
  margin: 60px 0;
}
</style>

<script>
 export default {
   name: 'Delimiter'
 }
</script>