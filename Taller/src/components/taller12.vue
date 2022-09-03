<template>
  <Div>
      <h1>Gana o pierde la materia?</h1>
      <br>
      <input type="text" v-model="name" placeholder="Nombre">
      <br>
      <input type="text" v-model="n1" placeholder="Nota 1">
      <br>
        <p v-if="n1<=5">
          <input type="text" v-model="n2" placeholder="Nota 2">
            <br>
        </p>
        <p v-else> Las notas van hasta 5</p>
        <p v-if="n2<=5">
            <input type="text" v-model="n3" placeholder="Nota 3">
            <br>
        </p>
        <p v-else> Las notas van hasta 5</p>
          <button @click="addstudent()"> Agregar Estudiante </button>
          <br>
        <ul>
          <li v-for="(student,index) in students" >
            <span>{{student.ans}}</span> 
          </li>
        </ul>
  </Div>
</template>


<script>
export default{
  name: 'Notas',
  data(){
    return {
      name:'',
      n1:'',
      n2:'',
      n3:'',
      avg:'',
      ans:'',
      students:[],
      student:{
          name: '',
          n1: '',
          n2: '',
          n3: '',
          avg: '',
          ans: ''
      },
      }
    },
    methods: {
      addstudent(){
        this.avg = (parseFloat(this.n1)+parseFloat(this.n2)+parseFloat(this.n3))/3;
        this.students.push({
          name: this.name,
          n1: this.n1,
          n2: this.n2,
          n3: this.n3,
          avg: this.avg,
          ans: this.avg >= 3 ? `${this.name}: Gano la materia`: `${this.name}: Perdio la materia`});
        this.name = '';
        this.n1 ='';
        this.n2 = '';
        this.n3 = '';
        this.avg = '';
        this.ans = '';
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
