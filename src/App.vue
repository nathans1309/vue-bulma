<template>
  <div id="app">
    <switch-buttons name="myswitch"></switch-buttons>

    <modal v-if="isActive" @close="closeModal">
      <h1>Here is my modal</h1>
    </modal>
    <button @click="showModal">show modal</button>

    
    <tabs>
      <tab name="contact" :selected="true">
        <h1>Contact Information</h1>
      </tab>
      <tab name="about">
        <h1>About Information</h1>
      </tab>
      <tab name="Detail">
        <h1>Detail Information</h1>
      </tab>
    </tabs>    

  </div>
</template>

<script>
import SwitchButtons from './components/SwitchButtons';
import Modal from './components/Modal';
import Tabs from './components/Tabs';
import Tab from './components/Tab';

export default {
  name: 'app',
  components: {
    SwitchButtons,
    Modal,
    Tabs, 
    Tab
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
