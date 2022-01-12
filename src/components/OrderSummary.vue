<template>
  <div :class="$style.orderSummary">
    <div :class="$style.heading">Order summary</div>
    <div :class="$style.row">
      <div :class="$style.orderItem">
        <span :class="$style.image">
          <IconBooks />
        </span>
        <div :class="$style.info">
          <h5 :class="$style.title">
            Advocate Premium Profile
            <span :class="$style.amount">$29</span>
          </h5>
          <p :class="$style.description">
            242 pages of insights and advice. Instant PDF download and online access, with e-reader versions also available.
          </p>
        </div>
      </div>
    </div>
    <div :class="$style.row">
      <CustomCheckbox v-model:checked="hasDiscountCode">
        I have a discount code
      </CustomCheckbox>
    </div>
    <div :class="$style.row">
      <h4 :class="$style.price">
        <span>Total</span>
        <span>$29</span>
      </h4>
      <button :class="$style.button">
        <IconSalesMoneyBackGuarantee />
        <span>30-day money-back guarantee</span>
      </button>
    </div>
  </div>
</template>

<style module lang="less">
.orderSummary {
  padding: 45px 40px 40px;
  border-radius: 10px;
  box-shadow: 0 10px 40px 0 rgba(29, 36, 50, 0.1);
  background-color: var(--backgroundBase);
  border-top: 5px solid var(--green-0);
  margin-bottom: 40px;
}

.heading {
  font-family: 'Open Sans', sans-serif;
  font-size: 14px;
  font-weight: 700;
  line-height: 1.86;
  text-transform: uppercase;
  margin-bottom: 10px;
}

.row {
  padding: 20px 0;
  border-top: 1px solid var(--grey-5);

  &:last-child {
    padding-bottom: 0;
  }
}

.orderItem {
  display: grid;
  grid-template-columns: 60px 1fr;
  grid-column-gap: 20px;

  .image {
    max-width: 100%;
  }

  .info {}

  .title {
    position: relative;
    padding-right: 50px;
  }

  .amount {
    position: absolute;
    top: 50%;
    right: 0;
    transform: translateY(-50%);
  }

  .description {
    font-size: 14px;
    line-height: 1.86;
  }
}

.price {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.button {
  display: flex;
  width: 100%;
  gap: 6px;
  align-items: center;
  height: 56px;
  padding: 15px 14px 15px 20px;
  margin: 20px 0 0;
  border-radius: 10px;
  border: solid 1px var(--grey-4);
  background-color: var(--backgroundBase);
  font-size: 14px;
  font-weight: 700;
  line-height: 1.86;
  text-align: left;
  transition: opacity 200ms ease-in-out;

  &:hover,
  &:focus,
  &:active {
    opacity: 0.8;
  }
}
</style>

<script>
import { ref } from "vue";
import CustomCheckbox from "./forms/CustomCheckbox.vue";
import IconSalesMoneyBackGuarantee from "./icons/IconSalesMoneyBackGuarantee.vue";
import IconBooks from "./icons/IconBooks.vue";

export default {
  name: 'OrderSummary',
  components: { IconBooks, IconSalesMoneyBackGuarantee, CustomCheckbox },
  setup() {
    const hasDiscountCode = ref(false);

    return {
      hasDiscountCode,
    };
  }
}
</script>