<template>
  <div>
      <h1>Login</h1>

        <form>
          <label for="email">Email</label>
          <input type="email" name="email" id="email" v-model="email">
            <br>
          <label for="password">Contrasena</label>
          <input type="password" name="password" id="password" v-model="password"> 
          <br>
          <label for="">Selecciona</label>
          <select name="select">
            <option v-for="(item, index) in posts" :key="index" :value="item.id">{{item.title}}</option>
          </select>       
        </form>

      <hr>
      {{saludo}}
      <br>
      <h2></h2>
      <Button :title='buttonTitle' :funcion="login" />
      <Button title='Cancelar' :funcion="cancelar" />
      <br>
      <Posts :arreglodePosts="posts"/>
  </div>
</template>

<script>
import Button from '../components/Button.vue'
import Posts from '../components/Posts.vue'
export default {
  layout: 'simple',
  components: {
    Button,
    Posts
  },
  data: () => ({
    email: 'gfjfghgh',
    password: '',
    buttonTitle: 'Login',
    nombre: 'Ivan',
    apellido: 'Rodriguez',
    posts: []
  }),
  computed: {
    saludo() {
      return this.nombre + ' ' + this.apellido
    }
  },
  created(){
    this.consultaApi();
  },
  methods: {
    async consultaApi () {
      try {
        const {data} = await this.$axios.get('https://jsonplaceholder.typicode.com/posts')
        this.posts = data;
      } catch (error) {
        console.log(error);
      }
    },
    login () {
      console.log('El usuario se ha logueado');
    },
    cancelar () {
      console.log('El usuario ha cancelado el login');
    }    
  }
}
</script>

<style>

</style>