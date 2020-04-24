<template>
  <div id="cities">
    <ul>
      <li v-for="(city,index) in cities" v-bind:key="index" v-on:click="city.show =!city.show">
        <h2>{{ city.name }}</h2>
        <h3 v-show="city.show">{{ city.speciality }}</h3>
      </li>
    </ul>
    <button v-on:click="deleteCity">Delete City</button>
  </div>
</template>

<script>
export default {
  props: {
    cities: {
      type: Array,
      required: true
    }
  },
  data(){
    return {

    }
  },
  methods: {
    deleteCity: function(){
      this.cities.pop();
    }
  }
}
</script>

<style scoped>
#cities{
  width: 100%;
  max-width: 1200px;
  margin: 40px auto;
  padding: 0 20px;
  box-sizing: border-box;
}
ul{
  display: flex;
  flex-wrap: wrap;
  list-style-type: none;
  padding: 0;
}
li{
  flex-grow: 1;
  flex-basis: 300px;
  text-align: center;
  padding: 30px;
  border: 1px solid #222;
  margin: 10px;
}

</style>
