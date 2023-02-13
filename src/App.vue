<script setup>
import { ref,onMounted,watch,computed } from 'vue';
import Header from './components/Header.vue';
import Cards from './components/Cards.vue'
import api from './api/api'
import moment from 'moment'

const posts = ref([])

onMounted(()=> {
  api.get('posts').then(res => {
    posts.value = res.data.map(p => {
      return{
        ...p,
        date_published: moment(p.date_published).format('ll')
      }
    })
  })
})


</script>

<template>
  <div class="container">    
      <Header/>
      <Cards 
      v-for="(p, index) in posts" 
      :key="index"
      :post="p"
      />
  </div>
</template>

