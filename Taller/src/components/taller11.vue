<template>
  <h1>¿Ganas o no Ganas el semestre?</h1>
  <br>
  <input type="text" v-model="notas.nombre" placeholder="Nombre" @keyup.enter="process">
  <br>
  <input type="number" v-model="notas.nota1" placeholder="Nota 1" @keyup.enter="process">
  <br>
  <input type="number" v-model="notas.nota2" placeholder="Nota 2" @keyup.enter="process">
  <br>
  <input type="number" v-model="notas.nota3" placeholder="Nota 3" @keyup.enter="process">
  <br>
  <h1>{{notas.nombre}} usted {{notas.respuesta}}</h1>
</template>
<script>
export default{
  name: 'Numeros',
  data(){
    return {
      notas: {
        nombre: '',
        nota1: '',
        nota2: '',
        nota3: '',
        prom: '',
        respuesta: ''
      }

    }
  },
  methods:{
    process(){
      this.notas.prom = (parseFloat(this.notas.nota1)+parseFloat(this.notas.nota2)+parseFloat(this.notas.nota3))/3;
      if(this.notas.prom >= 3){
        this.notas.respuesta = 'Gano la materia'
      }
      else if(parseFloat(this.notas.prom) < 3, parseFloat(this.notas.prom) >= 0) {
        this.notas.respuesta = 'Perdio la materia pai'
      }
    }
  }
}

</script>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
