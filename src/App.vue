
<script>
  export default {
    name: 'App',
    data(){
      return {       
        logoIron:"images/Ironhack_logovue-lab.png",
        containers:"cajita",
      };
    },
  };
</script>

<template>
  <div id="app">

    <nav-bar class="flex justify-between ml-7 mr-7 mt-7">
    </nav-bar>

    <header class="font-bold">
      Esto sera el Header
    </header>

    <main class="flex">
     Esto sera el Main
    </main>

    <footer>
      Esto sera el footer
    </footer>

  </div>
</template>


<style>
  .cajita{
    width: 25%;
    align-items: center;
   }
</style>