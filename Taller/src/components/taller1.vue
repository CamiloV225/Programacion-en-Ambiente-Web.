<template>
  <h1>Calculadora de segundos a hh:mm:ss</h1>
  <br>
  <input type="Digite los segundos?" v-model="sec" placeholder="Segundos" @keyup.enter='hora'>
  <br>
  <h2> Hora: {{horas}} Minutos: {{minutos}} Segundos: {{segundos}}</h2>
</template>
<script>

export default{
  name: 'segundos',
  data(){
    return {
      horas: '',
      minutos:'',
      sec:'',
      segundos:''
    }
  },  
  methods: {
    hora(){
      this.horas = Math.floor(this.sec/3600)
      this.minutos = Math.floor(this.sec/60)%60
      this.segundos = Math.round(this.sec)%60
    }
  },
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
