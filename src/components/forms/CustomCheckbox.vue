<template>
  <label :class="$style.checkbox">
    <input
        @input="(event) => $emit('update:checked', event.target.checked)"
        type="checkbox"
        :checked="checked"
        :class="$style.checkboxInput"
    />
    <span :class="$style.checkboxState">
      <span :class="$style.checkboxControl">
        <span :class="$style.checkboxIcon">
          <IconCheck />
        </span>
      </span>
      <span :class="$style.checkboxTitle">
        <slot />
      </span>
    </span>
  </label>
</template>

<style module lang="less">
.checkbox {
  position: relative;
  display: inline-block;
}

.checkboxState {
  cursor: pointer;
  display: flex;
  align-items: center;
}

.checkboxControl {
  width: 30px;
  height: 30px;
  border-radius: 5px;
  box-shadow: inset 0 2px 0 0 rgba(81, 89, 106, 0.05);
  border: solid 1px var(--borderPrimary);
  background-color: var(--backgroundBase);
  position: relative;
}

.checkboxIcon {
  display: none;
  color: var(--white);
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.checkboxInput {
  outline: none;
  position: absolute;
  clip: rect(0 0 0 0);
  opacity: 0;
}

.checkboxInput:checked ~ .checkboxState .checkboxControl {
  border-color: var(--borderAction);
  background-color: var(--backgroundAction);
}

.checkboxInput:checked ~ .checkboxState .checkboxIcon {
  display: inline-flex;
}

.checkboxTitle {
  margin: 0 0 0 15px;
  font-family: 'Open Sans', sans-serif;
  font-size: 18px;
  line-height: 1.67;
  color: var(--foregroundDefault);
}
</style>

<script>
import IconCheck from "../icons/IconCheck.vue";

export default {
  name: 'CustomCheckbox',
  components: { IconCheck },
  props: {
    checked: {
      type: Boolean,
    },
  }
}
</script>