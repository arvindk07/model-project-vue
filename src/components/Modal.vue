<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>Default Content</slot>
      <div class="action">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
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
  background: rgb(6, 136, 223);
}
.modal.sale h1 {
  color: white;
}
.modal.sale p {
  color: white;
}

.modal .action a {
  color: #333;
  padding: 8px;
  border: 1px solid #fff;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}
</style>
