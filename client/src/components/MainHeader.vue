<template>
  <header>
    <img src="@/assets/logo.webp" alt="">
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/blog">Blog</RouterLink>
      <RouterLink to="/admin">Admin</RouterLink>
    </nav>
  </header>
</template>

<script setup>
  import { RouterLink } from 'vue-router'
</script>