<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div v-if="!state.hidden">
    <test v-for="(num, index) in array" :key="index" :message="state.message" />
  </div>
  <Button :method="changeMessage"> Change Message </Button>
  <Button v-if="!state.hidden" :method="toggleMessages"></Button>
  <Button v-else :method="toggleMessages">Display Messages</Button>
</template>

<script>
import { reactive } from "vue";
import Test from "./components/Test";
import Button from "./components/Button";
export default {
  name: "App",
  components: {
    Test,
    Button,
  },
  setup() {
    const state = reactive({
      message: "this is my component",
      hidden: true,
    });
    return {
      state,
      array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
      changeMessage() {
        state.message = "this is a new message!";
      },
      toggleMessages() {
        state.hidden = !state.hidden;
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
