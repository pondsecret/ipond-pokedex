<template>
  <div>
    <header>
      <h1 style="color:#fff; margin-bottom:0px; margin-top:1-px">iPOND</h1>
      <img style="width:80px" src="./assets/pokeball_icon.png"> 
      <h1 style="color:#000; margin-top:-10px">Pokemons Studio</h1>
    </header>
    <section class="pokemon-content-container">
      <h1>Pokemons List</h1>
      <PokemonList /> 
    </section>
  </div>
</template>

<script>
// import InsertPokemonForm from './components/InsertPokemonForm.vue'
import PokemonList from './components/PokemonList.vue'

export default {
  name: 'App',
  components: {
    PokemonList,
  },
 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

header {
  box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10rem ;
  border: 5px solid #000;
  background: linear-gradient(180deg ,#FB1B1B 50%,#000 10%,#FFFFFF 55%);
}

header h1{
  font-size: 40px;
  text-shadow: 0px 2px 2px #000;
}
.pokemon-content-container{
  box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 2rem;
  border: solid;
  border-width: 10px;
  border-top-color:#0075BE;
  border-left-color: #0075BE;
  border-right-color:#fc0;
  border-bottom-color: #fc0;
}

.pokemon-content-container h1{
  font-size: 2.5rem;
  font-weight: 900;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color:#0A285F;
  border-bottom: 5px groove #0A285F;
  margin: 10px 20px 2rem 20px;
  border-radius: 4px;
  opacity: .8;
  padding: .5rem;
}
</style>
