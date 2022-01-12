<template>
  <Layout>
    <Header title="Checkout" />
    <Main :class="$style.checkoutPageWrapper">
      <PageNav />
      <Container>
        <div :class="$style.checkoutFormWrapper">
          <CheckoutForm />
          <div>
            <OrderSummary />
            <Review />
          </div>
        </div>
        <Delimiter />
        <InfoSection />
      </Container>
    </Main>
    <Footer />
  </Layout>
</template>

<style module lang="less">
.checkoutFormWrapper {
  display: grid;
  grid-template-columns: 50% 1fr;
  grid-column-gap: 132px;
  padding: 20px 0 0;
}
.checkoutPageWrapper {
  padding-bottom: 80px;
}
</style>

<script>
import Layout from "../components/Layout.vue";
import PageNav from "../components/PageNav.vue";
import Header from "../components/Header.vue";
import Main from "../components/Main.vue";
import CheckoutForm from "../components/CheckoutForm.vue";
import Footer from "../components/Footer.vue";
import OrderSummary from "../components/OrderSummary.vue";
import Review from "../components/Review.vue";
import Delimiter from "../components/Delimiter.vue";
import InfoSection from "../components/InfoSection.vue";
import Container from "../components/Container.vue";

export default {
  name: 'CheckoutPage',
  components: {
    Container,
    InfoSection,
    Delimiter,
    Review,
    OrderSummary,
    Footer,
    CheckoutForm,
    Main,
    Header,
    PageNav,
    Layout
  },
}
</script>