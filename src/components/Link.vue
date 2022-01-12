<template>
  <a :href="href" :class="$style.link">
    <slot />
  </a>
</template>

<style module lang="less">
.link {
  color: var(--foregroundAction);
  transition: opacity 200ms ease-in-out;
  text-decoration: none;
  display: inline-flex;
  align-items: center;

  &:hover,
  &:focus,
  &:active {
    opacity: 0.8;
  }
}
</style>

<script>
export default {
  name: 'Link',
  props: {
    href: String,
    className: String
  }
}
</script>