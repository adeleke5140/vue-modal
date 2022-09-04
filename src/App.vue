<template>
  <h1>trFm_🎉</h1>
  <button @click.shift="toggleModal" @click.alt="toggleModal2">
    1🙄 || 2🥵
  </button>
  <teleport to=".modals">
    <Modal v-if="showModal1" :toggleModal="toggleModal" @close="toggleModal">
      <template v-slot:links>
        <div>
          <a href="#"> sign up </a>
          <a href="#"> more info </a>
        </div>
      </template>
      <h3>Sign up for the giveaway🥳</h3>
      <p>Grab your swag for half price!</p>
    </Modal>

    <Modal v-if="showModal2" :toggleModal="toggleModal2" @close="toggleModal">
      <h3>Welcome to the new world!</h3>
      <p>This is future, sike!</p>
    </Modal>
  </teleport>
</template>

<script setup>
import { ref } from "vue"
import Modal from "./components/Modal.vue"

const showModal1 = ref(false)
const showModal2 = ref(false)

const toggleModal = () => (showModal1.value = !showModal1.value)

const toggleModal2 = () => (showModal2.value = !showModal2.value)
</script>

<style>
h1 {
  text-align: center;
  font-family: "Comfortaa", cursive;
  color: black;
  padding-top: 60px;
  color: rgba(255, 255, 255, 0.87);
}

p {
  margin-bottom: 10px;
}

#app,
.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #2c3e50; */

  background: #242424;
  height: 100vh;
  width: 100%;
}
</style>
