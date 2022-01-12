<template>
  <section :class="$style.section">
    <InfoBlock
        title="Safe"
        description="We don't record your card details. They'll be sent over a secure, encrypted channel."
        has-icon
    >
      <IconInfoSafe />
    </InfoBlock>
    <InfoBlock
        title="One-time payment"
        description="No sneaky renewals or hidden fees. Pay once and focus on learning, not reading small print."
        has-icon
    >
      <IconInfoUser />
    </InfoBlock>
    <InfoBlock
        title="30-day money-back guarantee"
        description="Didn't find your profile useful? Just let us know and we'll give you your money back."
        has-icon
    >
      <IconInfoMoneyBack />
    </InfoBlock>
    <InfoBlock
        title="Trusted by 27,500+ readers"
        description="The 500+ testimonials we've received really do speak for themselves. Check them out!"
        has-icon
    >
      <IconInfoUsers />
    </InfoBlock>
  </section>
</template>

<style module lang="less">
.section {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-column-gap: 32px;
}
</style>

<script>
import InfoBlock from "./InfoBlock.vue";
import IconInfoSafe from "./icons/IconInfoSafe.vue";
import IconInfoUser from "./icons/IconInfoUser.vue";
import IconInfoMoneyBack from "./icons/IconInfoMoneyBack.vue";
import IconInfoUsers from "./icons/IconInfoUsers.vue";

export default {
  name: 'InfoSection',
  components: {
    IconInfoUsers,
    IconInfoMoneyBack,
    IconInfoUser,
    IconInfoSafe,
    InfoBlock
  }
}
</script>