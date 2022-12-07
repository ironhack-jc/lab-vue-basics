
<template>
  <div id="app">
    <nav-bar class="flex justify-between ml-7 mr-7 mt-7">
      <img :src="logoIron" alt="Logo IronHack">
      <h4>Week-4-Day-2</h4>
    </nav-bar>

    <header class="text-center font-bold">
      <h1 class="text-3xl p-10">Hola guys :=)</h1>
    </header>

    <main class="text-center">
      <p class="p-4 font-bold text-2xl">{{ `Mi proyecto favorito es: ${array[0].name}`}} </p>
      <p class="p-4 font-bold text-2xl">{{ `El precio de crear un proyecto similar andaria por los ${array[0].price * 100}`}}</p>

      <div class="text-center p-3 font-bold text-1xl">Los proyectos activos son :</div> 

      <section v-for="(item) of active()" :key="item.uuid" class="text-center p-2">     
        <div class="text-center">{{` ${item.name} --- ${item.description}===> $${item.price * 100}`}}</div>  
                   
      </section>

      <div class="text-center p-2 font-bold text-2xl">Los proyectos de ofereta son :</div> 

      <section v-for="(item) of lowPrice()" :key="item.uuid" class="text-center p-2">       
        <div class="text-center">{{` ${item.name} --- ${item.description}===> $${item.price * 100}`}}</div>             
      </section>

      <section v-for="(item) of active()" :key="item.uuid" class="text-center">       
        <section class="text-center p-3 font-bold text-2xl" v-if="item.price > 50 ">{{`Nuestro proyecto estrella Es: ${item.name}`}}</section>         
      </section>

     
     
    </main>

    <footer class="text-center p-7">
      Gracias por apreciar nuestro trabajo 
    </footer>
  </div>
</template>

<script>
  import datos from "./items.json";
  export default {
    name: 'App',
    data(){
      return {       
        containers:"cajita",
        logoIron:"../public/images/Ironhack_logovue-lab.png",
        array: datos,
      };
    },

  computed:{ 

   },

   methods: {
    lowPrice(){
      return this.array.filter(item => item.price < 5);
    },
    active(){
      return this.array.filter(item => item.active == true);
    },    
   },

  };
</script>

<style>
  .cajita{
    width: 25%;
    align-items: center;
   }
</style>