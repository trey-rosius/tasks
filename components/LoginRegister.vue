<template>
  <div class="container">
    <Logo />
    <Login />
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";
import Login from "~/components/Login.vue";
export default {
  components: {
    Logo,
    Login
  }
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: space-around;
  align-items: center;
}
</style>
