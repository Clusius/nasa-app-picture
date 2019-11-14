<template>
  <div class="search">
    <form v-on:submit.prevent="getResult(query)">
      <input type="text" placeholder="Search a picture" v-model="query" />
    </form>
    <div class="é" v-if="results.length === 20">
    </div>
    <div v-if="results">
      <div v-for="result in results" class="resultat">
        <p class="title">{{result.data[0].title}}</p>
        <img v-bind:src="result.links[0].href"/>
        <p class="text">{{result.data[0].description}}</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import axios from 'axios'

export default Vue.extend({
  name: 'search',
  data () {
    return {
      msg: 'Search',
      query: '',
      results: []
    }
  },
  methods: {
    getResult(query){
      axios.get('https://images-api.nasa.gov/search?q=' + query +'&media_type=image').then(response => {
        this.results.push(response.data.collection.items[0]);
        console.log(response.data.collection)
      });
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.search {
  display: flex;
  flex-direction: column;
  align-items: left;
  justify-content: center;
  width: auto;
  text-align: center;
}

form {
    text-align: center;
    margin-bottom: 15px;
}


input[type=text], select {
  width: 50%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
p {
  font-size: 1.5rem;
  color: black;
}

.title {
  font-size: 2em;
  font-weight: bold;
  color: grey;
  text-align: center;
  text-shadow: #000000 1px 0 1px;
  font-family: 'Trebuchet MS';
}

.text {
 width: 90%;
 text-align: center;
 font-family: 'Times New Roman', Times, serif;

}

.resultat {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 365px;
  border: 1px solid grey;
  border-radius: 10%;
  text-align: center;
  margin-bottom: 20px;
}
img {
  width: 350px;;
}

</style>
