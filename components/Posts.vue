<template>
  <div>
    <h1>Listado de posts</h1>
    <div v-for="(post, index) in arreglodePosts" :key="index">
      <PostItem :post="post" />
    </div>
  </div>
  
</template>

<script>
import PostItem from './PostItem.vue'
export default {
  props: {
    arreglodePosts: Array
  },
  components: {
    PostItem
  }
}
</script>

<style>

</style>