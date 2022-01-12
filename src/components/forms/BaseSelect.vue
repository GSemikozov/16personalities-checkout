<template>
  <div>
    <div :class="$style.inputWrapper">
      <label v-if="label" :for="id" class="label" :class="$style.label">
        {{ label }}
      </label>
      <select v-model="modelValue" :id="id" :class="$style.select">
        <option v-if="defaultValue" selected disabled>{{ defaultValue }}</option>
        <option v-for="option in options" :value="option.value">
          {{ option.text }}
        </option>
      </select>
    </div>
  </div>
</template>

<style module lang="less">
.inputWrapper {
  position: relative;
  display: grid;
  grid-row-gap: 5px;
}

.select {
  height: 60px;
  min-width: 75px;
  max-width: 100%;
  padding: 15px 25px;
  border-radius: 5px;
  box-shadow: 0 1px 1px 0 rgba(81, 89, 106, 0.05);
  border: solid 1px var(--grey-4);
  background-color: var(--grey-6);
  outline: none;
  transition: all 200ms ease-in-out;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  background-image: url("data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTgiIGhlaWdodD0iMTgiIHZpZXdCb3g9IjAgMCAxOCAxOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxwYXRoIGQ9Im04LjcwMSAxMi4yMjctNS4yMDMtNS4xNmEuNDIyLjQyMiAwIDAgMSAwLS41OThsLjY5Ni0uNjk2YS40MjIuNDIyIDAgMCAxIC41OTggMEw5IDkuOTM5bDQuMjA4LTQuMTY2YS40MjIuNDIyIDAgMCAxIC41OTggMGwuNjk2LjY5NmEuNDIyLjQyMiAwIDAgMSAwIC41OTdsLTUuMjAzIDUuMTYxYS40MjIuNDIyIDAgMCAxLS41OTggMHoiIGZpbGw9IiM1MTU5NkEiIGZpbGwtcnVsZT0iZXZlbm9kZCIgb3BhY2l0eT0iLjUiLz4KPC9zdmc+Cg==");
  background-repeat: no-repeat;
  background-position-x: calc(100% - 20px);
  background-position-y: 21px;
  background-size: 18px;

  &:focus, &:active {
    box-shadow: 0 0 6px 0 rgba(80, 169, 170, 0.3), inset 0 2px 0 0 rgba(81, 89, 106, 0.05);
    border: solid 1px var(--borderAction);
  }
}
</style>

<script>
export default {
  name: 'BaseSelect',
  props: {
    id: {
      type: String,
      default: "",
    },
    label: {
      type: String,
      default: "",
    },
    options: {
      type: [Array],
      required: true,
    },
    modelValue: {
      type: [String, Number],
      default: "",
    },
    defaultValue: {
      type: [String],
      default: "",
    }
  },
}
</script>