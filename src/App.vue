<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <VueDragger :onDragStart="start" :onDragEnd="stop">
  </VueDragger>
  <HelloWorld msg="Make your components draggable with ease." />
</template>

<script>
import HelloWorld from "@/components/HelloWorld.vue";
import VueDragger from "@/components/VueDragger.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    // VueDragger,
  },
  methods: {
    start() {
      console.log("Starting Drag!");
    },
    stop() {
      console.log("Stopping Drag!");
    },
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
