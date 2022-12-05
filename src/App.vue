<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="name" />
  <button @click="handleClick">click me</button>

  <teleport to="#modals" v-if="showModal">
    <Modal @close="toggleModal">      
      <h1>Sign Up for Jan-jan Giveaway!</h1>
      <p>Enter and earn $50/day</p>

      <template v-slot:links>
        <a href="#">See more</a>
        <a href="#">More info</a>
      </template> 
    </Modal>
  </teleport>
  
  <teleport to="#modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign Up Newsletter!</h1>
      <p>For updates and promo codes!</p>

      <template v-slot:disclaimer>
        <p>
          [The author] assumes no responsibility or liability for any errors or omissions in the content of this site. The information contained in this site is provided on an "as is" basis with no guarantees of completeness, accuracy, usefulness or timeliness..."
        </p>
      </template>
    </Modal>
  </teleport>
  <p></p>


  <button @click="toggleModal">show modal</button>
  <button @click="toggleModalTwo">show modal 2</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
  data() {
    return {
      title: 'My First Vue App :)',
      showModal: false,
      showModalTwo: false
    }
  },

  methods: {
    handleClick(){
      console.log(this.$refs.name);
      this.$refs.name.classList.add('active');
      this.$refs.name.focus();
    },

    toggleModal(){
      this.showModal = !this.showModal;
    },

    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo;
    }
  }
}
</script>

<style>
#app,#modals{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
