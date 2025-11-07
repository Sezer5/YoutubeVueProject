<template>
  <div>  
    
    <div class="container">
      <h1 class="title">Youtube Uygulaması</h1>
      <SearchBar @termChange="onTermChange"/>
    </div>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
export default {
  name: 'App',
  components: {
      SearchBar
  },
  methods:{
      onTermChange(searchTerm){
          console.log(searchTerm);
      }
  }
}
</script>

<style>
    *{
      box-sizing: border-box;
      margin: 0;
    }
    .container{
      max-width: 1200px;
      width: 100%;
      margin: 50px auto;
    }
    .title{
      text-align: center;
    }
</style>
