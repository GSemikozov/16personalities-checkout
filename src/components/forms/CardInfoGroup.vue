<template>
  <fieldset :class="$style.cardInfo">
    <legend class="legend" :class="$style.cardInfoTitle">Card information</legend>
    <div :class="$style.cardNumber">
      <BaseInput
          placeholder="1234 1234 1234 1234"
          name="cc-number"
          model-value=""
          autocomplete="cc-number"
          inputmode="numeric"
          pattern="[\d ]{10,30}"
      />
      <span :class="$style.cardNumberIcons">
        <img
            src="/icons/credit-card-icons.png"
            srcset="
              /icons/credit-card-icons.png 1x,
              /icons/credit-card-icons@2x.png 2x,
              /icons/credit-card-icons@3x.png 3x
            "
            alt="payment cards"
        />
      </span>
    </div>
    <div :class="$style.expireDate">
      <BaseInput
          placeholder="MM / YY"
          name="cc-exp"
          model-value=""
          autocomplete="cc-exp"
          maxlength="5"
      />
    </div>
    <div :class="$style.cvcCode">
      <BaseInput
          placeholder="CVC code"
          name="cc-csc"
          model-value=""
          autocomplete="cc-csc"
          inputmode="numeric"
          maxlength="3"
      />
    </div>
  </fieldset>
</template>

<style module lang="less">
.cardInfo {
  display: grid;
  grid-template-columns: 1fr 175px;
  grid-gap: 10px;
  grid-template-areas: "title title"
                        "cardNumber cardNumber"
                        "expireDate cvcCode";
}

.cardInfoTitle {
  grid-area: title;
}

.cardNumber {
  grid-area: cardNumber;
  position: relative;
}

.cardNumberIcons {
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%);
  display: grid;
  grid-column-gap: 5px;
  pointer-events: none;
}

.expireDate {
  grid-area: expireDate;
}

.cvcCode {
  grid-area: cvcCode;
}
</style>

<script>
import BaseInput from "./BaseInput.vue";

export default {
  name: 'CardInfoGroup',
  components: { BaseInput }
}
</script>