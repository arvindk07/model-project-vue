<template>
  <h1>{{ title }}</h1>
  <!-- <input type="text" ref="name" /> -->
  <!-- <button @click="handleClick">Click Me</button> -->
  <br />
  <p>Welcome...</p>
  <Teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up</a>
        <a href="#">More Info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price</p></Modal
    >
  </Teleport>

  <Teleport to=".modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign Up to Newsletter</h1>
      <p>For Update and promo codes!</p></Modal
    >
  </Teleport>

  <button @click.alt="toggleModal">Open Modal (alt)</button>
  <button @click="toggleModalTwo">Open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My First App",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline;
  padding-bottom: 10px;
}
</style>
