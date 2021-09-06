<template>
  <div id="app">
    <hr>
    <h2>{{titulo}}</h2>
    <div class="container">
      <div class="form">
        <div class="form-group">
          <label for="">Nombre</label>
          <input type="text" class="form-control" v-model="registro.nombre">
        </div>
        <div class="form-group">
          <label for="">Colegio</label>
          <input type="text" class="form-control" v-model="registro.colegio">
        </div>
        <button class="btn-primary btn" @click="agregarEstudiante">Guardar</button>
      </div>
      <hr>
      <div class="row">
        <div class="col-5" v-for="(registro,i) in registros" :key="i">
          <div class="card">
            <div class="card-body">
              <div class="form-group">
                <h2>{{registro.nombre}}</h2>
                <hr>
                <p>{{registro.colegio}}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      titulo: 'Welcome to eduvallve',
      registro: {
        nombre: '',
        colegio: ''
      },
      registros:[
        /* registro de prueba {
          nombre: 'Juan Pérez',
          colegio: 'Juan XXV'
        } */
      ]
    }
  },
  methods:{
    agregarEstudiante:function(){
      const {nombre, colegio} = this.registro;
      this.registros.push({
        nombre,
        colegio
      });
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
