<template>
  <h1>A continuacion Digite 3 numeros diferentes</h1>
  <br>
  <input type="num1" v-model="num1" placeholder="Nr1" @keyup.enter="process">
  <br>
  <input type="num2" v-model="num2" placeholder="Nr2" @keyup.enter="process">
  <br>
  <input type="num3" v-model="num3" placeholder="Nr3" @keyup.enter="process">
  <br>
  <h2>{{respuesta}}</h2>
</template>
<script>
export default{
  name: 'Numeros',
  data(){
    return {
      num1: '',
      num2: '',
      num3:'',
      respuesta:''
    }
  },
  methods:{
    process(){
      if (this.num1 == this.num2){
        this.respuesta = 'El numero 1 y el numero 2 son iguales'
      }
      else if (this.num1 == this.num3){
        this.respuesta = 'El numero 1 y el numero 3 son iguales'
      }
      else if (this.num2 == this.num3){
        this.respuesta = 'El numero 2 y el numero 3 son iguales'
      }
      else if (this.num2 == this.num3 == this.num1){
        this.respuesta = 'Los numeros 1, 2 y 3 son iguales'
      }
      else{
        this.respuesta = 'Ninguno de los numeros son iguales'
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
