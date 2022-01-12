<template>
  <form @submit="handleSubmit" role="form">
    <section :class="$style.formSection">
      <h3 :class="$style.formSectionTitle">Contact information</h3>
      <div :class="$style.formGroup">
        <BaseInput
            label="E-mail address"
            type="email"
            id="email"
            name="email"
            placeholder="your.email@gmail.com"
            model-value=""
        />
      </div>
      <div :class="$style.formGroup">
        <CustomCheckbox v-model:checked="isGiftOn">
          <span :class="$style.checkboxText">This is a gift</span>
          <IconQuestionCircle />
        </CustomCheckbox>
      </div>
    </section>
    <section :class="$style.formSection">
      <h3 :class="$style.formSectionTitle">Payment method</h3>
      <div :class="$style.formGroup">
        <PaymentMethodOptions
            id="paymentMethod"
            :options="payment_method_options"
            v-model="paymentMethod"
            value="card"
            @handlePaymentMethodChange="handlePaymentMethodChange"
        />
      </div>
      <div :class="$style.formGroup" v-if="isCreditCard">
        <CardInfoGroup />
      </div>
      <div :class="$style.formGroup" v-if="isCreditCard">
        <BaseInput
            label="Name on card"
            type="text"
            id="card-name"
            name="cc-name"
            placeholder="E.g. Jane Smith"
            model-value=""
            autocomplete="cc-name"
            pattern="[\p{L} \-\.]+"
        />
      </div>
      <div :class="$style.formGroup" v-if="isNotApplePay">
        <BaseSelect
            label="Country"
            id="country"
            name="country"
            defaultValue="Select country"
            :options="country_select_options"
            v-model="country"
        />
      </div>
    </section>
    <div :class="$style.buttonsBar">
      <ButtonPrimary>
        <span :class="$style.submitButtonText">Pay & Download</span>
        <IconArrowRight />
      </ButtonPrimary>
      <span :class="$style.buttonsBarInfo">
        <IconLock />
        Secure payment
      </span>
    </div>
  </form>
</template>

<style module lang="less">
.formSection + .formSection {
  margin-top: 60px;
}

.formSectionTitle {
  margin-bottom: 20px;
}

.formGroup + .formGroup {
  margin-top: 20px;
}

.checkboxText {
  display: inline-flex;
  margin-right: 15px;
}

.buttonsBar {
  display: flex;
  gap: 10px;
  align-items: center;
  margin-top: 30px;
}

.buttonsBarInfo {
  display: inline-flex;
  align-items: center;
  grid-column-gap: 6px;
  font-family: 'Open Sans', sans-serif;
  font-size: 14px;
  font-weight: 700;
  line-height: 1.86;
  color: var(--foregroundDefault);
  text-transform: uppercase;
}

.submitButtonText {
  margin-right: 10px;
}
</style>

<script>
import BaseInput from "./forms/BaseInput.vue";
import CustomCheckbox from "./forms/CustomCheckbox.vue";
import IconQuestionCircle from "./icons/IconQuestionCircle.vue";
import PaymentMethodOptions from "./forms/PaymentMethodOptions.vue";
import CardInfoGroup from "./forms/CardInfoGroup.vue";
import BaseSelect from "./forms/BaseSelect.vue";
import ButtonPrimary from "./ButtonPrimary.vue";
import IconArrowRight from "./icons/IconArrowRight.vue";
import IconLock from "./icons/IconLock.vue";
import { ref } from "vue";

export default {
  name: 'CheckoutForm',
  components: {
    IconLock,
    IconArrowRight,
    ButtonPrimary,
    BaseSelect,
    CardInfoGroup,
    PaymentMethodOptions,
    IconQuestionCircle,
    CustomCheckbox,
    BaseInput
  },
  methods: {
    handlePaymentMethodChange(value) {
      this.selectedPaymentMethod = value;
    }
  },
  data() {
    return {
      country: "",
      paymentMethod: "", // ["card", "paypal", "applepay"]
      selectedPaymentMethod: "card",
      payment_method_options: [
        {
          icons: [
            "/icons/visa.svg",
            "/icons/mastercard.svg",
            "/icons/american-express.svg"
          ],
          value: "card",
          name: "Credit card",
        },
        {
          icons: [
            "/icons/paypal.svg"
          ],
          value: "paypal",
          name: "PayPal",
        },
        {
          icons: [
            "/icons/apple-pay.svg"
          ],
          value: "applepay",
          name: "Apple Pay",
        },
      ],
      country_select_options: [
        {
          value: "usa",
          text: "USA",
        },
        {
          value: "uk",
          text: "UK",
        },
      ]
    }
  },
  computed: {
    isCreditCard() {
      return this.selectedPaymentMethod === "card";
    },
    isNotApplePay() {
      return this.selectedPaymentMethod !== "applepay";
    }
  },
  setup() {
    const isGiftOn = ref(false);

    return {
      isGiftOn,
      handleSubmit(e) {
        e.preventDefault();
      }
    };
  },
}
</script>