<template>
  <h1>Calculadora minutos</h1>
  <br>
  <input type="Minutos" v-model="minus" placeholder="Minutos" @keyup.enter='hora'>
  <br>
  <h2>Minutos Consumidos: {{a}} Coste: ${{coste}}</h2>
</template>
<script>

export default{
  name: 'Minutos',
  data(){
    return {
      minus:'',
      coste:'',
      minimo: 3,
      def:'',
      a:''
    }
  },  
  methods: {
    hora(){
      if (Math.floor(this.minus <= 3)){
        this.coste = 100
        this.a = this.minus
      }
      else if (Math.floor(this.minus > 3)){
        this.def = (Math.floor(this.minus-this.minimo)*50)
        this.coste = (Math.floor(this.def+100))
        this.a = this.minus
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
