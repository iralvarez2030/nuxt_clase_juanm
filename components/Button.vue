<template>
  <div>
    <button @click.prevent="funcion">{{title}}</button>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    color: String,
    funcion: Function
  },
};
</script>

<style>
</style>