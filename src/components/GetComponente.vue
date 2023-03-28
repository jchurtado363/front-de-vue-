<template>
  <div>
    <h1> Lista de  persona registradas</h1>
    <table class="table table-primary table-bordered border-primary">
      <thead>
        <tr class="table_warning">
          <th>ID</th>
          <th>NOMBRE</th>
           <th>APELLIDO</th>
          <th>N_DOCUMENTO</th>
          <th>N_FICHA</th>
          <!-- <th>ACCION</th> -->
        </tr>
      </thead>
      <tbody>
        <tr v-for="cliente in clientes" v-bind:key="cliente">
            <td>{{cliente.idcliente}}</td>
            <td>{{cliente.name}}</td>
            <td>{{cliente.apellido}}</td>
            <td>{{cliente.n_ficha}}</td>
            <td>{{cliente.n_documento}}</td>
          
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  name: "GetComponente",
  data() {
    return {
      clientes: [],
    };
  },
  async mounted() {
    await this.axios
      .get("http://localhost:3000/appi/cliente")
      .then((response) => {
        this.clientes = response.data;
        console.log(response.data);
      })
      .catch((e) => {
        console.log(e);
      });
  },
};
</script>
<style scoped>
</style>
