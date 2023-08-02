<template>
 <div>
   <h1>Latest Movie</h1>
    <div class="input">
      <input type="search" v-model="search">
      <button @click="getposts">search</button>
    </div>

    <div class="result">
      <ul>
        <li v-for="post in post" :key="post">{{ post }}</li>
      </ul>
    
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return{
      post: [],
      search:''
    }
  },
  methods: {
    getposts(){
      fetch(`http://www.omdbapi.com/?i=tt3896198&apikey=ea8b573d`)
      .then(Response => Response.json())
      .then(data => this.post = data)
    }
  }
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  color: black;
  margin-top: 60px;
}

.result{
  background-color: yellow;
}
</style>