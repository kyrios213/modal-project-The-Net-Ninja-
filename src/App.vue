<template>
  <h1>{{ title }}</h1>
  <p>Welcome....</p>
  <!-- <input type="text" ref="name" />
  <button @click="handleClick">Click Me</button> -->
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <button @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from "@/components/Modal";

export default {
  name: "App",
  data() {
    return {
      title: "My First Vue App :)",
      header: "Sign up for the Giveaway!",
      text: "Grab your ninja swag for half price!",
      showModal: false,
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
