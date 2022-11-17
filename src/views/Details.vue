<template>
    <div v-if="error" class="error">
        <h1>{{error}}</h1>
    </div>
    <div v-else class="post">
        <div v-if="post">
            <h3>{{ post.title }}</h3>
            <p class="pre">{{post.body}}</p>
        </div>
        <div v-else>Blog is loading...</div>
    </div>
</template>

<script>
import getPost from "../composables/getPost"
export default {
    props: ['id'],
    setup(props) {
        const{post, error, load} = getPost(props.id)
        load()
        return { post, error}
    }
}
</script>

<style>
body {
    background-color: antiquewhite;
}
.post {
    max-width: 1200px;
    margin: 0 auto;
    background-color: rgba(236, 240, 241, 1);
    border-radius: 10px;
    padding: 5px 20px;
}
.post p {
    color: #444;
    line-height: 1.5em;
    margin-top: 40px;
}
.pre {
    white-space: pre-wrap;
}
</style>
