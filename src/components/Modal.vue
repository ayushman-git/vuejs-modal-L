<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ diff: theme === 'violet' }" ref="modal">
      <slot></slot>
      <div>
        <slot name="list"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.modal {
  width: 400px;
  padding: 20px;
  margin: 200px auto;
  background: white;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

h1 {
  color: brown;
}

.diff {
  background-color: purple;
  color: white;
}

.diff > h1 {
  color: white;
}
</style>