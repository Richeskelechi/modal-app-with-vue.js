<template>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleShow">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h3>Ninja Giveaway</h3>
      <p>Grab Your ninja swag for half price</p>
    </Modal>
  </teleport>
  <teleport to=".modals" v-else>
    <button @click="toggleShow">Show Modal</button>
  </teleport>

  <teleport to=".modals" v-if="showModalTwo">
    <Modal theme="sale" @close="toggleShowTwo">
      <template v-slot:links>
        <a href="#">sign up now For</a>
        <a href="#">more info</a>
      </template>
      <h3>Ninja Giveaway For Modal Two</h3>
      <p>Grab Your ninja swag for half price now</p>
    </Modal>
  </teleport>
  <teleport to=".modals" v-else>
    <button @click="toggleShowTwo">Show Modal Two</button>
  </teleport>
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
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleShow() {
      this.showModal = !this.showModal;
    },
    toggleShowTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app,
.modals {
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
button {
  background: #bbb;
  padding: 10px;
  border: none;
  border-radius: 4px;
  margin: 10px;
  font-size: 16px;
  color: #333;
}
</style>
