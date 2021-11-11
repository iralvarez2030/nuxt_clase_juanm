<template>
  <div>
    <h1>{{post.title}}</h1>
    <br/>
    <hr/>
    <h2>{{post.body}}</h2>
  </div>
</template>

<script>
export default {
  props: {
    post: Object
  }
}
</script>

<style>

</style>