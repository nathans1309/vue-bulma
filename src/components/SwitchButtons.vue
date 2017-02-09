<template>
  <div>
    <p class="control has-addons">
        <slot></slot>
    </p>

    <p class="control is-hidden">
      <label class="radio" v-for="btn in buttons">
        <input type="radio" :value="btn.value" v-model="picked" :name="name">
      </label>
    </p>
  </div>
</template>

<script>
  export default {
    name: 'SwitchButtons',
    props: { 
      name: {required:true} 
    },
    
    data() {
      return {
        picked:'',
        buttons: []
      }
    },

    methods: {
      selectButton(selectedBtn) {
        this.picked = selectedBtn.value;
        this.buttons.forEach(btn => {
          btn.isActive = (btn == selectedBtn);
        })
      }
    },

    created() {
      this.buttons = this.$children;
    }
    
  }
</script>

<style scoped>

</style>
