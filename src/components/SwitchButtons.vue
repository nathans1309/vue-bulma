<template>
  <div>
    <p class="control has-addons">
      <a v-for="btn in buttons" class="button" v-bind:class="{'is-active': (btn==picked)}" @click.prevent="picked=btn">
        <span>{{btn}}</span>
      </a>
    </p>

    <p class="control is-hidden">
      <label class="radio" v-for="btn in buttons">
        <input type="radio" :value="btn" v-model="picked" :name="name">
      </label>
    </p>
  </div>
</template>

<script>
  export default {
    name: 'SwitchButtons',
    props: { name: {required:true} },
    data() {
      return {
        picked: 'No',
        buttons: ['Yes','No']
      }
    }
    
  }
</script>

<style scoped>

</style>
