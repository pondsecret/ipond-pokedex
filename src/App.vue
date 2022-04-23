<template>
  <div>
    <header>
      <h1 style="color:#fff; margin-bottom:0px; margin-top:1-px">iPOND</h1>
      <img style="width:80px" src="./assets/pokeball_icon.png"> 
      <h1 style="color:#000; margin-top:-10px">Pokemons Studio</h1>
    </header>
    <div class="form-container">
      <FormTemplate @onPassed="getInput"/>
    </div>
    <section class="pokemon-content-container">
      <h1>Pokemons List</h1>
      <PokemonList :pokemons="pokemon"/> 
    </section>
  </div>
</template>

<script>
// import InsertPokemonForm from './components/InsertPokemonForm.vue'
import PokemonList from './components/PokemonList.vue'
import FormTemplate from './components/FormTemplate.vue'
export default {
  name: 'App',
  components: {
    PokemonList,
    FormTemplate
  },
  data(){
    return {
       pokemon: [
            {id:1,name:"Togepi",type:"Fairy",pid:175,isVisible:false,rate:2,
            img:"https://assets.pokemon.com/assets/cms2/img/pokedex/full/175.png",
            info:{
                height: 1,
                weight: 3.3,
                gender: "Male or Famale",
                ability: ["Serene Grace", "Hustle"],
                weakness: ['Steel', 'Poison']
            }},

            {id:2,name:"Pikachu",type:"Electric",pid:25,isVisible:false,rate:5,
            img:"https://assets.pokemon.com/assets/cms2/img/pokedex/full/025.png",
            info:{
                height: 1.33,
                weight: 13.2,
                gender: "Male or Famale",
                ability: ["Static"],
                weakness: ['Ground']
            }},

            {id:3,name:"Groundon",type:"Ground",pid:383,isVisible:false,rate:3,
            img:"https://assets.pokemon.com/assets/cms2/img/pokedex/full/383.png",
            info:{
                height: 11.5,
                weight: 2094.4,
                gender: "Unknown",
                ability: ["Drought"],
                weakness: ['Water', 'Grass', 'Ice']
            }},

            {id:4,name:"Mewtwo",type:"Physic",pid:150,isVisible:false,rate:4,
            img:"https://assets.pokemon.com/assets/cms2/img/pokedex/full/150.png",
            info:{
                height: 1,
                weight: 3.3,
                gender: "Unknown",
                ability: ["Pressure"],
                weakness: ['Ghost', 'Dark', 'Bug']
            }},

            {id:5,name:"Stakataka",type:"Rock, Steel",pid:805,isVisible:false,rate:1,
            img:"https://assets.pokemon.com/assets/cms2/img/pokedex/full/805.png",
            info:{
                height: 1,
                weight: 3.3,
                gender: "Unknown",
                ability: ["Beast Boost"],
                weakness: ['Water', 'Fighting', 'Ground']
            }}

            ]
    }
  },
  methods:{
    getInput(input){
      const inputObject = {
        id: this.pokemon.length+1,
        name: input.name,
        type: input.type,
        pid: input.pid,
        isVisible: false,
        rate: 3,
        img: input.image_url,
        info:{
          height: input.height,
          weight: input.weight,
          gender: input.gender,
          ability: input.abilities,
          weakness: input.weakness,
        }
      }
      this.insertPokemon(inputObject)
    },
    insertPokemon(inputObj){
      if(!this.pokemon.push(inputObj)){
        console.log("Push input data Error")
      }
    }
  }
 
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
