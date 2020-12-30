<template>
  <input type="text" ref="name" />
  <button @click="submit">Submit</button>
  <p>{{ name }}</p>
  <button @click.shift="toggleModal">Modal (Shift + Click)</button>
  <Modal
    @close="toggleModal"
    v-if="showModal"
    :theme="theme"
  >
  <template v-slot:list>
    <ul>
      <li>Generated</li>
      <li>using</li>
      <li>named</li>
      <li>Slots</li>
    </ul>
  </template>
    <h1>Title</h1>
    <p>This is the content</p>
  </Modal>
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
