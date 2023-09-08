<template>
  <h1>{{ title }}</h1>
  <p>welcome...</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
          <a href="">sign up now</a>
          <a href="">more info</a>
      </template>
      <h1>Sign up from more kities</h1>
      <p>grab your kitie and pray for the price</p>
    </Modal>
    
  </teleport>
  <div v-if="showModal2">
    <Modal theme="" @close="toggleModal2">
      <template v-slot:links>
          <a href="">sign up now</a>
          <a href="">more info</a>
      </template>
      <h1>Sign up from the newsletter</h1>
      <p>for updates and promosssss!</p>
    </Modal>
    
  </div>
  <button @click="toggleModal" class="btn">modal teleport</button>
  <button @click="toggleModal2" class="btn">open modal</button>
</template>

<script>

import { Teleport } from 'vue'
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal, Teleport },
  data() {
    return {
      title: 'my first vue app',
      header: 'Sign up from more kities',
      text:'grab your kitie and pray for the price',
      showModal:false,
      showModal2:false
    }
  },
  methods: {
    HandleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
      
    },
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2
    }
  },
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
.btn{
  padding: 15px 7px;
  margin: 10px;
  border: 1px solid black;
  background-color: #2c3e50;
  color: aliceblue;
  border-radius: 16px;
}
</style>
