<template>
        <li><img :src="imageUrl"></li>
        <div>{{video.snippet.title}}</div>
</template>

<script>
export default {
    props:['video'],
    computed:{
        imageUrl(){
            return this.video.snippet.thumbnails.medium.url;
        }
    }
}
</script>

<style>

</style>