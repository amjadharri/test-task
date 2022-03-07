<template>
  <div id="app">
    <NavBar />
    <div class="body">
      <BodyWrapper />
      <TheWidget />
    </div>
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import TheWidget from "./components/TheWidget.vue";
import BodyWrapper from "./components/BodyWrapper.vue";
export default {
  name: "App",
  components: {
    NavBar,
    TheWidget,
    BodyWrapper,
  },
  data() {
    return {};
  },
};
</script>
<style lang="scss" scoped>
#app {
  width: 100%;
  height: 100%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  .body {
    @apply h-full flex;

    @include mobile {
      @apply flex-col-reverse overflow-y-auto;
    }
  }
}
</style>
