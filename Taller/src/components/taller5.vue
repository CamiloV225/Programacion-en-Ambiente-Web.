<template>
  <div>
      <h1> {{title}} </h1>
      <p> Ingrese un numero y presione enter. </p>
      <input @keypress.enter="arrPush()" type="number" v-model="num" id="a"><br/>
      <ul>
      <li v-for="(item) in items">
          <span> {{item}} </span>
      </li>
      </ul>
      <p> (Presione el botón para ordenar los números)</p>
      <button @click="orderList()"> Ordenar </button> <br/>
  </div>

</template>
<script>
export default {
  name: "MinToMax",
  data(){
      return{
          title: "List Ordering",
          num: 0,
          items:[
          ]
      }
  },
  methods: {
      orderList(){
          return this.items.sort((a,b)=>a-b);
      }
  },
  computed: {
      arrPush(){
          return this.items.push(this.num);
      },
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
