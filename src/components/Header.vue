<template>
  <header :class="$style.header" role="banner">
    <div class="container" :class="$style.inner">
      <a href="/" :class="$style.logo">
        <Logo />
      </a>
      <div :class="$style.title">
        {{ title }}
      </div>
    </div>
  </header>
</template>

<style module lang="less">
.header {
  background-color: var(--backgroundBase);
  border-bottom: 1px solid var(--borderPrimary);
  padding: 18px 0;

  .inner {
    display: flex;
    align-items: center;
  }

  .logo {
    height: 54px;
    display: inline-flex;
  }

  .title {
    margin-left: 10px;
    font-family: 'Open Sans', sans-serif;
    font-size: 20px;
    color: var(--foregroundDefault);
  }
}
</style>

<script>
import Logo from "./Logo.vue";

export default {
  name: 'Header',
  components: { Logo },
  props: {
    title: String
  }
}
</script>