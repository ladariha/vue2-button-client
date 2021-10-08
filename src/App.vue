<template>
  <div id="app">
    <JsonEditorVue :modelValue.sync="obj" v-bind="obj" />
    <MyButton/>
    <p>Mouse: {{ x }}x{{ y }}</p>
  </div>
</template>

<script lang="ts">
import { MyButton } from "ladariha-button";
import JsonEditorVue from "json-editor-vue";
import { useMouse } from "@vue-demi/use-mouse";
import { defineComponent } from "@vue/composition-api";

export default defineComponent({
  name: "App",
  components: {
    JsonEditorVue, MyButton,
  },
  setup() {
    const {x, y} = useMouse();
    const obj = { a : 1}
    return {x, y, obj};
  },
});
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
