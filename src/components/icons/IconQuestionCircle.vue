<template>
  <span :class="$style.circle">
    <IconQuestion />
  </span>
</template>

<style module lang="less">
  .circle {
    width: 22px;
    height: 22px;
    border-radius: 50%;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    background-color: var(--backgroundAlt);
    color: var(--white);
  }
</style>

<script>
import IconQuestion from "./IconQuestion.vue";

export default {
  name: 'IconQuestionCircle',
  components: { IconQuestion }
}
</script>