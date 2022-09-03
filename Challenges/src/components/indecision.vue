<template>
  <img :src = 'img'>
  <div class="bg-dark"></div>
  <div class="indecision-container"></div>
      <input @type="text" v-model="question" placeholder="Hazme una Question">
      <p> Recuerda finalizar con signo de interrogación (?)</p>
          <h2>{{question}}</h2>
          <h2>{{ans}}</h2>
  
  
  <br>
  </template>
  
  <script>
    export default{
      name: 'Indecision',
      data () {
          return {
              question: '',
              img: '',
              ans: ''
              }
      },
      watch: {
          question(value,oldValue){
              console.log(value,oldValue);
              this.question.includes('?')? this.API(): null
          }
      },
      methods: {
        async API(){
          const api = await fetch('https://yesno.wtf/api')
          const data = await api.json();
          console.log(data)
          this.img = data.image;
          this.ans = data.answer;
                
        } 
      }
    }
  </script>
  
  
  <style scoped>
  h1 {
    font-weight: 500;
    font-size: 2.6rem;
    top: -10px;
    color:black;
  }
  p{
    color:black;
  }
  h2{
    color:black;
  }
  h3 {
    font-size: 1.2rem;
    color:black;
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
  button {
    background-color: #09ff11; /* Green */
    border: none;
    color: rgb(0, 0, 0);
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
  }
  </style>