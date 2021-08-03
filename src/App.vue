<template>
  <h1>{{ title }}</h1>
  <p>WELCOME</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up here!</a>
        <a href="#">more shit</a>
      </template>
      <h1>Giveaway</h1>
      <p>Sign Up!</p>
    </Modal>
  </teleport>

  <teleport to=".modals" v-if="showModal2">
    <Modal @close="toggleModal2">
      <h1>hello</h1>
      <p>world</p>
    </Modal>
  </teleport>
  <button @click="toggleModal">Toggle</button>
  <button @click="toggleModal2">Toggle2</button>
</template>

<script>
import Modal from "@/components/Modal";

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My first Vue app :)',
      header: 'Sign up for the giveaway',
      text: 'Grab my swag brother',
      showModal: false,
      showModal2: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
    }
  }
}
</script>

<style>
#app, .modals{
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
