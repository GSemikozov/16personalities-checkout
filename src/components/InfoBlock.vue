<template>
  <div :class="$style.infoBlock">
    <div v-if="hasIcon" :class="$style.icon">
      <slot />
    </div>
    <div>
      <h5 :class="$style.title">{{ title }}</h5>
      <p :class="$style.description">{{ description }}</p>
    </div>
  </div>
</template>

<style module lang="less">
.infoBlock {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.icon {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

.title {
  margin-bottom: 10px;
  font-family: 'Open Sans', sans-serif;
  text-align: center;
}

.description {
    font-size: 16px;
    line-height: 1.75;
    text-align: center;
}
</style>

<script>
export default {
  name: 'InfoBlock',
  props: {
    hasIcon: Boolean,
    title: String,
    description: String
  }
}
</script>