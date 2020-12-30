<template>
  <input type="text" ref="name" />
  <button @click="submit">Submit</button>
  <p>{{ name }}</p>
  <button @click.shift="toggleModal">Modal (Shift + Click)</button>
  <Modal @close="toggleModal" v-if="showModal" :theme="theme">
    <template v-slot:list>
      <ul>
        <li>Generated</li>
        <li>using</li>
        <li>named</li>
        <li>Slots</li>
      </ul>
    </template>
    <h1>This is the default slot</h1>
    <p>This is the content</p>
  </Modal>

  <button @click.alt="toggleModalTwo">Modal (Alt + Click)</button>

  <Modal @close="toggleModalTwo" v-if="showModalTwo">
    <template v-slot:list>
      <div class="another-box">Empty</div>
    </template>
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
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
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
