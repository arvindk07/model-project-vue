<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  border-radius: 10px;
  background: #fff;
}
.backdrop {
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
}
.modal h1 {
  color: #03cfb4;
  border-bottom: none;
  padding: 0;
}

.modal p {
  font-style: normal;
}

.modal.sale {
  background: black;
}
.modal.sale h1 {
  color: white;
}
.modal.sale p {
  color: white;
}
</style>
