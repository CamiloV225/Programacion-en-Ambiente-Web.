<template>
  <div>
      <h1> {{title}} </h1>
      <p> Digite un salario y presione Enter. <br/> (Ingrese 10) </p>
      <input @keypress.enter="arrPush()" type="number" v-model="newSalary" id="a"><br/>
      Presione el botón para ver los salarios con un aumento del 0.8%<br/>
      <button @click="customSal()"> +0.8% </button> 
      <ul v-for="(item, index) in newItems">
          <li> Salario {{index+1}}: {{item}} </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: "Salary",
  data(){
      return{
          title: "Salary calculator",
          newSalary: 0,
          items:[],
          newItems: []
      }
  },
  methods: {
      arrPush(){
          // console.log(this.items)
          return this.items.push(this.newSalary);
      },
      customSal(){
          if (this.items.length < 10){
              alert("Por favor ingrese los salarios restantes");
          }
          else if(this.items.length > 10){
              alert("Por favor ingrese exactamente 10 salarios");
          }
          else if (this.items.length == 10){
              this.newItems = this.items.map(x => x + x *0.8);
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
