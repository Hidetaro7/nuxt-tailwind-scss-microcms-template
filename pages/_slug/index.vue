<template>
  <main class="main">
    <h1 class="title">{{ sizes }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="summary"></div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://tuqulore.microcms.io/api/v1/instant/${params.slug}`,
      {
        headers: { 'X-API-KEY': 'c1567ee1-ca6e-4d8c-b1c7-0263a1130920' }
      }
    )
    console.log(data)
    return data
  }
}
</script>

<style lang="scss" scoped>
.main {
  p {
    @apply text-red-800;
  }
}
</style>
