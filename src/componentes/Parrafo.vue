<template>

  <section class="src-componentes-parrafo">
    <h1>Componente Parrafo</h1>
    <hr><hr>
    <div class="jumbotron">
      <label>Color:</label>
      <input type="text" v-model="color">
      <label>Fondo:</label>
      <input type="text" v-model="fondo">
      <label>Size:</label>
      <input type="text" v-model="size">
      <hr><br>
      <label>Texto:</label>
      <input v-model.trim="texto" :style="{'color': color, 'background-color': fondo, 'font-size': size}" >

      <p>Cantidad de palabras: {{ cantPalabras() }}</p>

      <h1>Cuestionario</h1>
      <hr>
      <hr>
      <br>
      <div v-if="preguntas.length" class="table-responsive">
        <table class="table">
          <tr>
            <th>Numero de pregunta</th>
            <th>Respuestas</th>
          </tr>
          <tr v-for="(pregunta, index) in preguntas" :key="index">
            <td>{{ pregunta.numero }} </td>
            <td>{{ pregunta.respuestas }} </td>
          </tr>
        </table>
      </div>
    </div>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-componentes-parrafo',
    props: [],
    mounted () {
      
    },
    data () {
      return {
        color: '',
        fondo: '',
        size: '',
        texto: ' ',
        preguntas: [
          { numero: 1, respuestas: ['b'] },
          { numero: 2, respuestas: ['c'] },
          { numero: 3, respuestas: ['b'] },
          { numero: 4, respuestas: ['d'] },
          { numero: 5, respuestas: ['d'] },
        ],
      }
    },
    methods: {
      cantPalabras(){
        let contador = 0
        if(!(this.texto=="")){
          let textoDividido = this.texto.split(" ");
          contador = textoDividido.length;
        }
        return contador;
      },
    },
    computed: {

    }
}


</script>

<style scoped lang="css">
  label{
    padding: 2px;
  }
  tr{
    color:black
  }
  td{
    color:black
  }
</style>
