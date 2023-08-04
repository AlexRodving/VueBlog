<script setup>
import ButtonSlot from '@/components/ButtonSlot.vue'
import ButtonProps from '@/components/ButtonProps.vue'
import ButtonMix from '@/components/ButtonMix.vue'
</script>

<template>
  <main>
    <div v-for="p of posts" :key="p._id">
      <h1>{{p.title}}</h1>
      <div class="flex">
        <div class="blogtext">
          <p>
            {{p.text}}
          </p>
          <a href="#" class="button">Discover now</a>
        </div>
        <div class="imgConteiner">
          <img :src="p.src" alt="">
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      posts: []
    }
  },
  async beforeMount() {
    const data = await fetch('http://127.0.0.1:3002/posts')
    const posts = await data.json()
    this.posts = posts.all
  }
}
</script>

<style>
  .blogtext {
    flex: 3;
  }
</style>
