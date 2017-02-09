<template>
  <div id="app">
    <switch-buttons name="myswitch">
      <switch-button :value="1" :selected="true">Button 1</switch-button>
      <switch-button :value="2" >Button 2</switch-button>
      <switch-button :value="3" >Button 3</switch-button>
    </switch-buttons>
<hr>
    <modal v-if="activeModal" @close="closeModal">
      <h1>Here is my modal</h1>
    </modal>
    <button @click="showModal">show modal</button>

    <hr>
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
<hr>
    <progress-bar maxValue="50"></progress-bar>
<hr>

  <data-table></data-table>

  </div>
</template>

<script>
import SwitchButtons from './components/SwitchButtons';
import Modal from './components/Modal';
import Tabs from './components/Tabs';
import Tab from './components/Tab';
import SwitchButton from './components/SwitchButton';
import ProgressBar from './components/ProgressBar';
import DataTable from './components/DataTable';

export default {
  name: 'app',
  components: {
    SwitchButtons,
    SwitchButton,
    Modal,
    Tabs, 
    Tab,
    ProgressBar,
    DataTable
  },
  data() {
    return {
      activeModal:false
    }
  },
  methods: {
    showModal() {
      this.activeModal = true;
    },
    closeModal() {
      this.activeModal = false;
    }
  }
}
</script>

<style>

</style>
