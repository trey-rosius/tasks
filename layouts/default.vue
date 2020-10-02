<template>
  <div>
    <Nuxt />
  </div>
</template>

<style lang="scss">
:root {
  --primary-color: #302ae6;
  --secondary-color: #e76f51;
  --font-color: #424242;
  --bg-color: #fff;
  --heading-color: #f4a261;
  --link-color: #2a9d8f;
  --tab-color: #2a9d8f;
  --input-color: #000000;
}

[data-theme="dark"] {
  --primary-color: #9a97f3;
  --secondary-color: #e76f51;
  --font-color: #e1e1ff;
  --bg-color: #161625;
  --heading-color: #f4a261;
  --link-color: #2a9d8f;
  --input-color: #ffffff;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

body {
  background-color: var(--bg-color);
  color: var(--font-color);

  max-width: 90%;
  margin: 0 auto;
  font-size: calc(1rem + 0.25vh);
  overflow: hidden;

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

h1 {
  color: var(--secondary-color);
  font-family: "Sansita One", serif;
  font-size: 2rem;
  margin-bottom: 1vh;
}

p {
  font-size: 1.1rem;
  line-height: 1.6rem;
}

a {
  color: var(--link-color);
  text-decoration: none;
  border-bottom: 3px solid transparent;
  font-weight: bold;
  &:hover,
  &:focus {
    border-bottom: 3px solid currentColor;
  }
}

section {
  max-width: 68%;
  margin: 0 auto;
}

.post-meta {
  font-size: 1rem;
  font-style: italic;
  display: block;
  margin-bottom: 4vh;
}

nav {
  display: flex;
  justify-content: flex-end;
  padding: 20px 0;
}
/*Simple css to style it like a toggle switch*/
.theme-switch-wrapper {
  display: flex;
  align-items: center;

  em {
    margin-left: 10px;
    font-size: 1rem;
  }
}
.theme-switch {
  display: inline-block;
  height: 34px;
  position: relative;
  width: 60px;
}

.theme-switch input {
  display: none;
}

.slider {
  background-color: #ccc;
  bottom: 0;
  cursor: pointer;
  left: 0;
  position: absolute;
  right: 0;
  top: 0;
  transition: 0.4s;
}

.slider:before {
  background-color: #fff;
  bottom: 4px;
  content: "";
  height: 26px;
  left: 4px;
  position: absolute;
  transition: 0.4s;
  width: 26px;
}

input:checked + .slider {
  background-color: #66bb6a;
}

input:checked + .slider:before {
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
</style>
