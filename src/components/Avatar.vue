<template>
  <div :class="$style.avatar">
    <img :src="src"  :class="$style.avatarImg" alt="avatar" />
  </div>
</template>

<style module lang="less">
.avatar {
  width: 80px;
  min-width: 80px;
  height: 80px;
  border-radius: 50%;
  overflow: hidden;
}

.avatarImg {
  height: 100%;
  width: 100%;
  object-fit: cover;
}
</style>

<script>
export default {
  name: 'Avatar',
  props: {
    src: String
  }
}
</script>