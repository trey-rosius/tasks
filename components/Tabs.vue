<template>
  <div class="demo">
    <nav>
      <div class="theme-switch-wrapper">
        <label class="theme-switch" for="checkbox">
          <input type="checkbox" id="checkbox" v-model="darkMode" />
          <div class="slider round"></div>
        </label>
        <em>Lights Out!</em>
      </div>
    </nav>
    <div class="tab-menu">
      <div
        v-for="tab in tabs"
        :key="tab"
        :class="['tab-button', { active: currentTab === tab }]"
        @click="currentTab = tab"
      >
        {{ tab }}
      </div>

      <component :is="currentTabComponent" class="tab"></component>
    </div>
  </div>
</template>

<script>
import Login from "@/components/Login.vue";
import Register from "@/components/Register.vue";
export default {
  data() {
    return {
      darkMode: false,
      currentTab: "Login to Account",
      tabs: ["Login to Account", "Create an Account"]
    };
  },

  computed: {
    currentTabComponent: function() {
      return this.currentTab === "Login to Account" ? "Login" : "Register";
    }
  },
  components: {
    Login,
    Register
  },
  watch: {
    darkMode: function() {
      // add/remove class to/from html tag
      let htmlElement = document.documentElement;

      if (this.darkMode) {
        htmlElement.setAttribute("data-theme", "dark");
      } else {
        htmlElement.setAttribute("data-theme", "light");
      }
    }
  }
};
</script>

<style scoped>
.tab-menu {
  align-self: center;
  width: 50%;
}
.demo {
  display: flex;
  flex-direction: column;

  align-content: space-between;
}
.tab-button {
  width: 50%;
  display: inline-block;
  font-weight: bold;
  text-align: center;
  padding: 6px 10px;

  cursor: pointer;
}

.tab-button.active {
  background: var(--tab-color);
}
.tab {
  margin-left: 3rem;
  margin-right: 3rem;

  padding: 10px;
}
</style>
