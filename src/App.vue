<template>
  <div id="app">
    <div class="top-bg-rectangle p-0 m-0" />
    <div class="container">
      <main-content />
    </div>
    <div class="bottom-bg-rectangle p-0 m-0" />
  </div>
</template>

<script>
import MainContent from "@/components/main-content";

export default {
  name: "App",
  components: {
    MainContent,
  },
};
</script>

<style lang="scss">
@import "assets/style";

#app {
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #565656;
  position: relative;
  font-weight: normal;

  .container {
    padding: 3em;
  }

  .top-bg-rectangle,
  .bottom-bg-rectangle {
    background-color: $blue;
    width: 100%;
    height: 7em;
    position: absolute;
    z-index: -1;
  }

  .bottom-bg-rectangle {
    bottom: 0;
  }
}
</style>
