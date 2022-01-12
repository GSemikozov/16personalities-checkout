<template>
  <CheckoutPage />
</template>

<script>
import Header from "./components/Header.vue";
import Layout from "./components/Layout.vue";
import Main from "./components/Main.vue";
import PageNav from "./components/PageNav.vue";
import CheckoutPage from "./pages/CheckoutPage.vue";

export default {
  name: '16P Checkout',
  components: {
    CheckoutPage,
    PageNav,
    Main,
    Layout,
    Header
  }
}
</script>
