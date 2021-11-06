<template>
  <h1>{{ title }}</h1>
  <p>Welcome....</p>
  <!-- <input type="text" ref="name" />
  <button @click="handleClick">Click Me</button> -->
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="/">Sign Up Now!</a>
        <a href="/">More info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:links>
        <a href="/">Check it out</a>
      </template>
      <h1>Welcome</h1>
      <p>Normal Modal Component</p>
    </Modal>
  </div>

  <p><button @click.alt="toggleModal">Open Sale Modal (alt)</button></p>
  <p><button @click="toggleModalTwo">Open Modal</button></p>
</template>

<script>
import Modal from "@/components/Modal";

export default {
  name: "App",
  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModalTwo: false,
    };
  },
  components: {
    Modal,
  },
  methods: {
    // handleClick() {
    //   console.log(this.$refs.name);
    //   this.$refs.name.classList.add("active");
    //   this.$refs.name.focus();
    // },
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
  display: inline-block;
  padding-bottom: 10px;
}
</style>
