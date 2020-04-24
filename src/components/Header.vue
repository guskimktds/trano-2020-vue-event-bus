<template>
  <header>
    <h1 v-on:click="changeTitle">{{ title }}</h1>
  </header>
</template>

<script>
import { bus } from '../main';
export default {
  props: {
    title: {
      type: String
    }
  },
  data(){
    return{
      //title: 'Vue KTds Platform'
    }
  },
  methods: {
    changeTitle: function(){
      //this.title = "Vue Wizards"
      //this.$emit('changeTitle','Vue Wizards');
      //this.title = 'Vue Bus Changed Wizards';
      bus.$emit('titleChanged', 'Vue Bus Changed Wizards');
    }
  }
}
</script>

<style>
header {
  background: lightblue;
  padding: 10px;
}
h1{
  color: #222;
  text-align: center;
}
</style>
