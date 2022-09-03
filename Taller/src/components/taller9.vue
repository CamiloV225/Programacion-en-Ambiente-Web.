<template>
  <h1>Digite el numero de filas y columnas que quiere que tenga la tabla</h1>
  <br>
  <input type="button" value="Add Bottom" onclick="addRow()"/>
  s<input type="button" value="Add Top" onclick="addRow(1)"/>
  <br>
  <div id="a">
    <tabla id ="b">

    </tabla>
  </div>
</template>

<script>
export default {
  name: "Salary",
  data(){
      return{
          filas:'',
          column:''
          
      }
  },
  methods: {
      addRow (top) {
  var table = document.getElementById("b");

  if (top) { var row = table.insertRow(0); }
  else { var row = table.insertRow(); }

  var cell = row.insertCell();
  cell.innerHTML = "AA";
  cell = row.insertCell();
  cell.innerHTML = "BB";
  }
    }
    }
    
  

</script>

<style scoped>
        table{
            border-collapse: collapse;
            border-spacing: 0;
        }
        th, td{
            padding: 10px 20px;
            border: 1px solid #000;
        }

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
