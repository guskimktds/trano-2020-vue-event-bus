<template>
  <div>
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
    <app-content v-bind:cities="cities"></app-content>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>

import Header from './components/Header.vue';
import Footer from './components/footer.vue';
import Content from './components/Content.vue';
import { bus } from './main';

export default {
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-content': Content
  },
  data(){
    return {
      cities: [
        {name: 'Seoul', speciality: 'Captial, is the capital of the Korea', show: false},
        {name: 'Tokyo', speciality: 'Captial, is the capital of the Japan', show: false},
        {name: 'New Delhi', speciality: 'Captial, is the capital of the India', show: false},
        {name: 'Washington', speciality: 'Captial, is the capital of the USA', show: false},
        {name: 'London', speciality: 'Captial, is the capital of the UK', show: false},
        {name: 'Paris', speciality: 'Capital and most populous city of France ', show: false}
      ],
      title: "Vue KTds"
    }
  },
  methods:{
    updateTitle: function(updateTitle){
      this.title = updateTitle;
    }
  },
  created(){
    bus.$on('titleChanged',(data) => {
      this.title = data;
    })
  }
}
</script>

<style>

</style>
