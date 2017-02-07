<template>
  <div id="app">
    <switch-buttons name="myswitch"></switch-buttons>

    <modal v-if="isActive" @close="closeModal">
      <h1>Here is my modal</h1>
    </modal>
    <button @click="showModal">show modal</button>

    
  </div>
</template>

<script>
import SwitchButtons from './components/SwitchButtons';
import Modal from './components/Modal';

export default {
  name: 'app',
  components: {
    SwitchButtons,
    Modal
  },
  data() {
    return {
      isActive:false
    }
  },
  methods: {
    showModal() {
      this.isActive = true;
    },
    closeModal() {
      this.isActive = false;
    }
  }
}
</script>

<style>

</style>
