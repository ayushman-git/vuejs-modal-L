<template>
  <input type="text" ref="name" />
  <button @click="submit">Submit</button>
  <p>{{ name }}</p>
  <Modal />
</template>

<script>
import Modal from "./components/Modal";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      name: "",
    };
  },
  methods: {
    submit() {
      const { name } = this.$refs;
      this.name = name.value;
      name.classList.add("input-class");
      name.focus();
    },
  },
};
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
