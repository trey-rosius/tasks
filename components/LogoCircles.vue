<template>
  <div class="circle">
    <icon-base
      width="150"
      height="150"
      icon-name="circle"
      class="circle__circle1"
    >
      <IconThreeDot
    /></icon-base>
    <icon-base
      width="120"
      height="120"
      icon-name="circle"
      class="circle__circle2"
    >
      <IconThreeDot
    /></icon-base>
    <icon-base
      width="120"
      height="120"
      icon-name="circle"
      class="circle__circle3"
    >
      <IconThreeDot
    /></icon-base>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.circle {
  position: relative;

  background-color: white;
  &__circle1 {
    position: absolute;
    left: 30px;
    color: var(--color-secondary-yellow);
  }
  &__circle2 {
    position: absolute;
    left: 10px;
    top: 20px;
    color: var(--color-primary-pink);
  }
  &__circle3 {
    position: absolute;
    left: 70px;
    top: 20px;
    color: var(--color-blue);
  }
}
</style>
