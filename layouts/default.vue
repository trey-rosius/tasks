<template>
  <div>
    <Nuxt />
  </div>
</template>

<style>
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

body {
  background-image: linear-gradient(
    to right bottom,
    var(--color-primary-pink),
    var(--color-secondary-yellow)
  );

  overflow: hidden;
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100vh;
  font-family: "Montserrat", -apple-system, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  line-height: 1.4;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

main {
  padding: 0;
  width: 95vw;
  margin-left: 2vw;
}

@media screen and (min-width: 1000px) {
  main {
    padding: 40px;
    width: 80vw;
    margin-left: 7vw;
  }
}
</style>
