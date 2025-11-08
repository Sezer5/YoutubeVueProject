<template>
        <div class="selectedVideoContainer" v-if="video">
            <div>
                <iframe :src="videoUrl" class="selectedVideo"></iframe>
            </div>
            <div class="details">
                <h4>{{video.snippet.title}}</h4>
                <p>{{video.snippet.description}}</p>
            </div>
        </div>
</template>

<script>
export default {
    props:['video'],
    computed:{
        videoUrl(){
            const {videoId} = this.video.id;
            return `https://www.youtube.com/embed/${videoId}`
        }
    }
}
</script>

<style scoped>
    .selectedVideoContainer{
        width: 100%;
    }
    .selectedVideo{
        width: 100%;
        height: 350px;
        border-radius: 30px;
    }
    .details{
        border: 1px solid gray;
        padding: 10px;
        margin-top: 10px;
        border-radius: 10px;
    }
</style>