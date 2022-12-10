<template>
<h1>{{ title }}</h1>
<p>Welcome.....!</p>
<!-- <br>
<input type="text" ref="name">
<button @click="handleRef">chnage ref</button> -->
  <div v-if="showModal">
 <Modal :header="header" :text="text"  theme="Sale" @click="toggleButton"/>
 
  </div>
  <button @click.right="toggleButton">open Modal</button>
  </template>

<script >

import Modal from './components/Modal.vue'

export default  {
  name : 'App' ,
  components : { Modal },
  data(){
    return {
      title :'My first vue app:',
      header :'sign up for the Giveaway',
      text: 'Grab your ninjs sawag for half prove!',
     showModal : false
    }
  },
  methods : {
  handleRef(){
   console.log(this.$refs.name)
   this.$refs.name.classList.add('active')
   this.$refs.name.focus()
  },
  toggleButton(){
    this.showModal = !this.showModal
  }
  }
}
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
</style>
