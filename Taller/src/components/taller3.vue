<template>
  <input type="Digite los segundos?" v-model="nomb" placeholder="Digite su nombre">
  <br>
  <h1>Digite la hora en formato 24 horas:</h1>
  <input type="Digite los segundos?" v-model="hora" placeholder="Hora" @keyup="psm">
  <br>
  <h2>{{saludo}} {{nomb}}</h2>
</template>
<script>
export default{
  name: 'Horas',
  data(){
    return {
      hora:'',
      nomb:'',
      saludo:''
    }
  },
  methods: {
    psm(){
      if (this.hora >= 1, this.hora <=12){
        this.saludo = 'Buenos dias:'
      }
      else if (this.hora >= 13, this.hora <18){
        this.saludo = 'Buenas Tardes:'
      }
      else if (this.hora >= 18, this.hora <=24){
        this.saludo = 'Buenas Noches:'
      }
      else {
        this.saludo = 'ERROR NIGGER'
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
