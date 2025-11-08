<template>
  <div>  
    
    <div class="container">
      <h1 class="title">Youtube Uygulaması</h1>
      <SearchBar @termChange="onTermChange"/>
      <VideoList :videos="videos"/>
    </div>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
import VideoList from './components/VideoList.vue';
import axios from 'axios'
export default {
  name: 'App',
  components: {
      SearchBar,
      VideoList
  },
  data(){
    return{
        videos:[],
    }
  },
  methods:{
      onTermChange(searchTerm){
          axios.get('https://www.googleapis.com/youtube/v3/search',{
            params:{
              part:'snippet',
              type:'video',
              key:'AIzaSyAYiYiSmdKooV0i4LXm1Hp-p0J-LINGK0s',
              q:searchTerm
            }
            
          })
            .then(response=> {
                this.videos = response.data.items;
            })
            .catch(response=>  {
                console.log(response);
            });
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
