<template>
  <footer  :class="$style.footer" role="contentinfo">
    <div class="container">
      <p :class="$style.copyright">©2011-2021 NERIS Analytics Limited</p>
      <nav :class="$style.footerNav">
        <Link href="#">Contact</Link>
        <Link href="#">Terms & Conditions</Link>
        <Link href="#">Privacy Policy</Link>
      </nav>
    </div>
  </footer>
</template>

<style module lang="less">
.footer {
  background-color: var(--backgroundBase);
  border-top: 1px solid var(--borderPrimary);
  padding: 60px 0 40px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.footerNav {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
}

.copyright {
  margin-bottom: 20px;
  font-size: 16px;
  line-height: 1.75;
  color: var(--foregroundSubtle);
  text-align: center;
}
</style>

<script>
import Link from "./Link.vue";

export default {
  name: 'Footer',
  components: { Link }
}
</script>