<template>
  <div :class="$style.inputWrapper">
    <label v-if="label" :for="id" class="label" :class="$style.label">
      {{ label }}
    </label>
    <input
        :id="id"
        :type="type"
        :value="modelValue"
        @input="updateInput"
        :class="$style.input"
        :placeholder="placeholder"
        :autocomplete="autocomplete"
        :pattern="pattern"
        :maxlength="maxlength"
        :inputmode="inputmode"
    />
  </div>
</template>

<style module lang="less">
  .inputWrapper {
    position: relative;
    display: grid;
    grid-row-gap: 5px;
  }

  .input {
    height: 60px;
    min-width: 75px;
    max-width: 100%;
    padding: 15px 25px;
    border-radius: 5px;
    box-shadow: inset 0 2px 0 0 rgba(81, 89, 106, 0.05);
    border: solid 1px var(--borderPrimary);
    background-color: var(--backgroundBase);
    outline: none;
    transition: all 200ms ease-in-out;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;

    &:focus, &:active {
     box-shadow: 0 0 6px 0 rgba(80, 169, 170, 0.3), inset 0 2px 0 0 rgba(81, 89, 106, 0.05);
     border: solid 1px var(--borderAction);
    }

    &::placeholder {
      color: var(--foregroundAlt);
    }
  }
</style>

<script>
export default {
  name: 'BaseInput',
  props: {
    id: {
      type: String,
      default: "",
    },
    name: String,
    label: {
      type: String,
      default: "",
    },
    placeholder: {
      type: String,
      default: "",
    },
    modelValue: {
      type: [String, Number],
      default: "",
    },
    type: {
      type: String,
      default: "text",
    },
    autocomplete: String,
    pattern: String,
    maxlength: [String, Number],
    inputmode: String
  },
  methods: {
    updateInput(event) {
      this.$emit("update:modelValue", event.target.value);
    }
  }
}
</script>