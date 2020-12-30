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

</style>
