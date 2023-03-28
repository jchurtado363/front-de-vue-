<template>
  <main class="btn btn-primary">
    <h1>Registrar nueva persona</h1>
    <form class="row g-3" @submit='postCliente()'>
      <div>
        <label for="nomcliente">Nombre</label>
        <input type="text" id="name" v-model="usuarioNvo.name" />
      </div>
      <div>
        <label for="rutcliente">Apellido</label>
        <input type="text" id="apellido" v-model="usuarioNvo.apellido" />
      </div>
      <div>
        <label for="rutcliente">Documento</label>
        <input type="text" id="n_documento" v-model="usuarioNvo.n_documento" />
      </div>
      <div>
        <label for="rutcliente">N.Ficha</label>
        <input type="text" id="n_ficha" v-model="usuarioNvo.n_ficha" />
      </div>
      <br>
      <br>
      <button class="">Crear</button>
    </form>
  </main>
</template>
<script>
import axios from 'axios';

export default {
  name: "PosComponente",

  data() {
    return {
      usuarioNvo: {
        name: '',
      apellido:'',
      n_documento:'',
      n_ficha:''  
      },
    };
  },
  methods: {
    postCliente() {
      axios
        .post("http://localhost:3000/appi/cliente", this.usuarioNvo)
        .then((response) => console.log(response));
    },
  },
};
</script>



<style scoped>
</style>