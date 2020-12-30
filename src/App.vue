<template>
  <input type="text" ref="name" />
  <button @click="submit">Submit</button>
  <p>{{ name }}</p>
  <button @click="toggleModal">Modal</button>
  <Modal
    @close="toggleModal"
    v-if="showModal"
    :header="header"
    :content="content"
    :theme="theme"
  />
</template>

<script>
import Modal from "./components/Modal";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      name: "",
      header: "Header for modal",
      content: "This is the content inside modal",
      theme: "violet",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
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
