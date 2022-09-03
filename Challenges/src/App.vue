<script>
  import indecision from '@/components/indecision.vue';
    export default{
      name: 'App',
      components: {
        indecision
  
      }
    }
  </script>
  
  <template>
    <indecision></indecision>
  </template>
  
  <style>
  body {
    background-color: rgb(105, 105, 105);
  }
  header {
    line-height: 1.5;
  }
  
  .logo {
    display: block;
    margin: 0 auto 2rem;
  }
  
  
  </style>