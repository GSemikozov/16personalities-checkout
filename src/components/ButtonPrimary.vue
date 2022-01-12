<template>
  <button :type="type" :class="$style.button">
    <slot />
  </button>
</template>

<style module lang="less">
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 60px;
  padding: 15px 40px;
  border-radius: 40px;
  background-color: var(--purple-0);
  transition: all 200ms ease-in-out;
  font-family: 'Open Sans', sans-serif;
  font-size: 18px;
  font-weight: 600;
  line-height: 1.67;
  color: var(--white);

  &:hover,
  &:active,
  &:focus {
    background-color: darken(#88619a, 20%);
  }
}
</style>

<script>
export default {
  name: 'ButtonPrimary',
  props: {
    type: String
  }
}
</script>