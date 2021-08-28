<template>
  <div class="panel">
    <div
      class="title-container"
      :class="!secondary ? 'bottom-border uppercase' : ''"
    >
      <h3 class="p-0 m-0 color-main">{{ title }}</h3>
    </div>
    <div class="panel-content m-0 p-0">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "panel",
  props: {
    title: {
      type: String,
      default: "",
    },
    secondary: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss" scoped>
.title-container {
  width: 100%;
  line-height: 1.25em;
  margin-bottom: 1em;

  h3 {
    margin-top: 1em;
  }

  .bottom-border {
    border-bottom: solid #979797 2px;
  }
}
</style>
