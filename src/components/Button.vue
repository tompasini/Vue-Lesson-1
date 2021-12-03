<template>
  <slot></slot>
  <button @click="method">Test</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    method: Function,
  },
  setup() {
    return {};
  },
};
</script>

<style>
</style>

