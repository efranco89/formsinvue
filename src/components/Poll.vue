<template>
  <div>

    <form>
      <div class="row">
        <div class="col-sm-8 col-md-6">
          <h1>Formulario de Contacto</h1>
          <hr>
          <div class="form-group">
            <label for="name">Nombre</label>
            <input type="text" id="name" class="form-control" v-model='personData.nombre'>
          </div>
          <!-- Ends name -->
          <div class="form-group">
            <label for="email">Email</label>
            <input type="text" id="email" class="form-control" v-model='personData.email'>
          </div>
          <!-- Ends email -->

        </div>
      </div>
    </form>

    <div class="row">
      <div class="col-sm-8 col-md-6">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h3>Datos</h3>
          </div>

          <div class="panel-body">
            <p>Nombre: {{ personData.nombre }} </p>
            <p>Correo: {{ personData.email }} </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'poll',
    data(){
      return {
        personData:{
          nombre: '',
          email: ''
        }

      }
    }
  }
</script>

<style>

</style>