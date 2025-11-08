<template>
        <ul>
                <VideoListItem v-for="video in videos" :key="video.etag" :video="video" />
        </ul>
</template>

<script>
import VideoListItem from './VideoListItem.vue';
export default {
    props:['videos'],
    components:{
        VideoListItem,
        }
}
</script>

<style>

</style>