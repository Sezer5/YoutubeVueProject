<template>
        <div>
            <div>
                <iframe src=""></iframe>
            </div>
            <div>
                <h4>{{video.snippet.title}}</h4>
                <p>{{video.snippet.description}}</p>
            </div>
        </div>
</template>

<script>
export default {
    props:['video'],
}
</script>

<style>

</style>