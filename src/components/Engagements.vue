<script setup>
    import { defineProps } from 'vue';

    const {
        likes,
        comments
    } = defineProps([
        'likes',
        'comments'
    ])

</script>

<template>
    <div class="engagements">
        <div class="likes">
            <p><i class='bx bxs-heart text-danger'></i> {{likes}}</p>
        </div>
        <div class="comments" v-for="(c, index) in comments" :key="index">
            <span>
                <p class="comment-info"><i class='bx bxs-user-circle'></i> {{c.name}}</p>
                <p class="comment-text">{{c.body}}</p>
            </span>
        </div>
    </div>
</template>