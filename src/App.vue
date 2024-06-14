<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
        <a href="">Sign up</a>
        <a href="">Info</a>
      </template>
      <h1>Hello world</h1>
      <p>smaller text</p>
    </Modal>
  </div>

  <div v-if="showModal2">
    <Modal @close="toggleModal2">
      <h1>New Modal</h1>
      <p>smaller text</p>
    </Modal>
  </div>

  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModal2">Open Modal 2</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModal2: false,
    };
  },

  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },

    toggleModal2(){
      this.showModal2 = !this.showModal2;
    }
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

<!-- NPM run serve -->
