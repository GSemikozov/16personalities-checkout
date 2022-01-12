<template>
  <div :class="$style.review">
    <div :class="$style.tooltip">
      “Reading the in-depth, detailed profile is a major learning curve on knowing,
      understanding and managing myself and the world I live in. The Profile is a
      roadmap to being happy. Equipped with this powerful information, I feel excited
      to embrace every piece of who I am and improve my life – thanks to the hard work,
      commitment and dedication of the team here.”
    </div>
    <div :class="$style.userInfo">
      <Avatar src="/icons/avatar.png" />
      <div class="h5">Grace</div>
    </div>
  </div>
</template>

<style module lang="less">
.review {}

.tooltip {
  padding: 30px 40px;
  margin-bottom: 27px;
  border-radius: 10px;
  background-color: var(--grey-7);
  font-family: 'Open Sans', sans-serif;
  font-size: 14px;
  line-height: 1.86;
  position: relative;

  &:after {
    content: '';
    border: 40px solid transparent;
    border-bottom: 27px solid var(--grey-7);
    position: absolute;
    top:  100%;
    left: 80px;
    transform: rotate(-25deg) translateY(-56px);
  }
}

.userInfo {
  display: grid;
  align-items: center;
  grid-template-columns: 80px 1fr;
  grid-column-gap: 20px;
}


</style>

<script>
import Avatar from "./Avatar.vue";

export default {
  name: 'Review',
  components: { Avatar }
}
</script>