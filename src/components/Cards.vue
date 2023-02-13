
<script setup>
    import { ref,defineProps } from 'vue';
    import Engagements from './Engagements.vue'
    const {post} = defineProps(['post'])

</script>

<template>
    <div class="blog-post">
        <div class="blog-post-image">
            <img :src="post.image" alt="photo">
        </div>
        <div class="blog-post-info">
            <div class="blog-post-date">
                <span>By: {{ post.author }} (Software Engineer)</span>
                <span>{{post.date_published}}</span>
            </div>
            <h1 class="blog-post-title">{{post.title}}</h1>
            <p class="blog-post-text">{{post.body}}</p>
            <a href="#" class="read-more">Read More</a>
        </div>
    </div>
    <Engagements :likes="post.likes" :comments="post.comments" />
</template>