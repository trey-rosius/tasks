<template>
  <div class="logo">
    <LogoCircles />

    <span class="title">TASKS</span>
  </div>
</template>
<script>
import LogoCircles from "~/components/LogoCircles.vue";
export default {
  components: {
    LogoCircles
  }
};
</script>

<style lang="scss" scoped>
.logo {
  display: flex;

  flex-direction: row;
  width: 20%;
  height: 130px;
  justify-content: space-around;
}
.title {
  font-weight: bold;
  font-size: 2rem;
  margin-top: 60px;
  margin-left: 90px;
  color: white;

  letter-spacing: 1px;
  font-family: "Montserrat", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
}
</style>
