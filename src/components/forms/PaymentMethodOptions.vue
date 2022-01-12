<template>
  <fieldset :id="id" :class="$style.container">
    <label v-for="(option) in options" :key="option.value">
      <input
          :name="id"
          type="radio"
          v-model="value"
          :value="option.value"
          :checked="option.value === value"
          :class="$style.optionInput"
          :disabled="disabled"
          :required="required"
          @change="updateValue(option.value)"
      />
      <span :class="[{ [$style.active]: option.value === value }, $style.option]">
        <span v-if="option.value === value" :class="$style.iconCheck">
          <IconCheck />
        </span>
        <span v-if="option.icons.length > 0" :class="$style.optionIcons">
          <img v-for="icon in option.icons" :src="icon" :key="option.value" :alt="option.name" />
        </span>
        <span :class="$style.optionTitle">{{ option.name }}</span>
      </span>
    </label>
  </fieldset>
</template>

<style module lang="less">
.container {
  display: grid;
  grid-template-columns: repeat(3, minmax(90px, 1fr));
  grid-column-gap: 30px;
  padding: 10px 0;
}

.optionInput {
  position: absolute;
  opacity: 0;
  clip: rect(0 0 0 0);
  outline: none;
}

.option {
  display: grid;
  height: 151px;
  position: relative;
  border-radius: 5px;
  box-shadow: inset 0 2px 0 0 rgba(81, 89, 106, 0.05);
  border: 1px solid var(--borderPrimary);
  align-items: end;
  cursor: pointer;

  &.active {
    border: 2px solid var(--borderAction);
  }
}

.iconCheck {
  position: absolute;
  top: -15px;
  right: -15px;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--white);
  background-color: var(--backgroundAction);
}

.optionIcons {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 15px;
}

.optionTitle {
  padding: 10px;
  text-align: center;
  font-family: 'Open Sans', sans-serif;
  font-size: 16px;
  font-weight: 600;
  line-height: 1.75;
  border-top: 1px solid var(--borderSecondary);
}

.option.active .optionTitle {
  margin-bottom: -1px;
}

.option.active .optionIcons {
  margin-top: -1px;
}
</style>

<script>
import IconCheck from "../icons/IconCheck.vue";
import { ref } from "vue";

export default {
  name: 'PaymentMethodOptions',
  components: { IconCheck },
  model: {
    event: 'change',
  },
  props: {
    id: {
      type: String,
      required: true,
    },
    value: {
      type: [String, Number, Boolean, Object],
      default: null
    },
    options: {
      type: [Array],
      required: true,
    },
    required: {
      type: Boolean,
      default: false,
    },
    disabled: {
      type: Boolean,
      default: false,
    }
  },
  methods: {
    updateValue(value) {
      this.$emit("handlePaymentMethodChange", value);
    },
  }
};
</script>