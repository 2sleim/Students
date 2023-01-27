<template>
  <div class="main" :class="{ white: isWhite, dark: !isWhite }">
    <div class="content">
      <router-view></router-view>
      <button @click="changeTheme" id="changeThemeButton">Змінити тему</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      isWhite: "",
    };
  },
  mounted() {
    this.isWhite = this.$store.getters.getTheme;
  },
  methods: {
    changeTheme() {
      this.isWhite = !this.isWhite;
      this.$store.commit("changeTheme", this.isWhite);
    },
  },
};
</script>
