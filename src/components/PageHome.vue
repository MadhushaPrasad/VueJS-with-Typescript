<template>
  <div>
    <h1>Hello Hee</h1>
    <div v-for="thread in threads" :key="thread.id">
      <h2>{{ thread.title }}</h2>
      <div v-for="postId in thread.posts" :key="postId">
        <p>{{ users.find(u => u.id === posts.find(p => p.id === postId).userId).name }}</p>
        <p>{{ posts.find(p => p.id === postId).text }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from '@/data.json'

export default {
  name: "PageHome"
  ,
  data() {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users
    }
  }
}
</script>

<style scoped>

</style>