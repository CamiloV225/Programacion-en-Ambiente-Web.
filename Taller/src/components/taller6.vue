<template>
  <div>
      <h1> {{title}}</h1>
      <input @keypress.enter="odd()" type="number" v-model="num" id="a" placeholder="Inserta un número"><br/>
      <h1> Los números impares menores que {{num}} son: {{this.nums}}</h1>
  </div>
</template>

<script>
export default {
  name: "OddNumber",
  data(){
      return{
          title:"ODD NUMBERS",
          nums: [],
          x:0
      }
  },
  methods: {
      odd(){
          while(this.x < this.num){
              if(this.x%2 != 0){
              this.nums.push(this.x)
              }
          this.x +=1
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
