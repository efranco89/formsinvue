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
      <div class="row">
        <div class="col-sm-8 col-md-6">
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" cols="58" rows="5" class="form-control"
              v-model="message">
            </textarea>
          </div>
        </div>
      </div>
      <!-- Ends messages -->

      <div class="row">
        <div class="col-sm-8 col-md-6">
          <div class="form-group">
            <label for="enviaremail">
              <input type="checkbox" id="enviaremail" value="enviarmail" v-model="mailOptions"> Enviar email
            </label>&nbsp;&nbsp;
            <label for="enviarmecopia">
              <input type="checkbox" id="enviarmecopia" value="enviarcopia" v-model="mailOptions"> Enviar copia
            </label>
          </div>
        </div>
      </div>
      <!-- Ends checkboxes -->

      <div class="row">
        <div class="col-sm-8 col-md-6">
          <div class="form-group">
            <label for="masculino">
              <input type="radio" id="masculino" value="M" v-model="gender"> Masculino
            </label>&nbsp;&nbsp;
            <label for="femenino">
              <input type="radio" id="femenino" value="F" v-model="gender"> Femenino
            </label>
          </div>
        </div>
      </div>
      <!-- Ends radiobuttons -->

      <div class="row">
        <div class="col-sm-8 col-md-6">
          
          <label for="horario"> Horario </label>
          <select id="horario" class="form-control" v-model="schedule">
            <option :value="item" v-for="item in scheduleData" :key="item"> {{ item }} </option>
          </select>
          
        </div>
      </div>
      <!-- Ends dropdown -->

      <div class="row">
        <div class="col-sm-8 col-md-6">
          <br>
          <button class="btn btn-primary" @click.prevent="sentMethod">Enviar</button>
        </div>
      </div>

    </form>
    <br>
    <div class="row" v-if="sent">
      <div class="col-sm-8 col-md-6">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h3>Datos ingresados</h3>
          </div>

          <div class="panel-body">
            <p>Nombre: {{ personData.nombre }} </p>
            <p>Correo: {{ personData.email }} </p>
            <p style="white-space:pre">Mensaje: <br> {{ message }} </p>
            <p>
              Opciones de Envio:
              <ul>
                <li v-for="item in mailOptions" :key="item"> 
                  {{ item }}
                </li>
              </ul>
            </p>
            <p>Genero: {{ gender }}</p>
            <p>Horario: {{ schedule }}</p>
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
        },
        message: 'Test de mensaje',
        mailOptions: [],
        gender: 'M',
        schedule: 'Manhana',
        scheduleData: ['Manhana', 'Tarde', 'Noche', 'Medio dia'], 
        sent: false

      }
    },
    methods: {
      sentMethod(){
        this.sent = true;
      }
    }
  }
</script>

<style>

</style>