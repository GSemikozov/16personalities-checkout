<template>
  <Container>
    <nav role="navigation">
      <Link href="#">
        <IconArrowLeft />
        <span :class="$style.text">Go back</span>
      </Link>
    </nav>
  </Container>
</template>

<style module lang="less">
.text {
  margin-left: 6px;
  font-weight: 700;
  font-size: 14px;
  line-height: 1.86;
  text-transform: uppercase;
}
</style>

<script>
import Link from "./Link.vue";
import IconArrowLeft from "./icons/IconArrowLeft.vue";
import Container from "./Container.vue";

export default {
  name: 'PageNav',
  components: { Container, IconArrowLeft, Link }
}
</script>