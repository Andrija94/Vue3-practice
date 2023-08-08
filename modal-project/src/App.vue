<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>

  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <h1>Ninja Givaway</h1>
      <p>Grab your ninja swag for half price!</p>
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
    </Modal>
  </teleport>

  <div v-if="showModal2">
    <Modal @close="toggleModal2">
      <h1>Second Modal</h1>
      <template v-slot:text>
        <p>Dummy text here</p>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal" >Open modal</button>
  <button @click="toggleModal2" >Open modal 2</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },

  data() {
    return {
      title: 'My First Vue App :D',
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
#app, .modals {
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
