<template>
  <div>
      <ul>
          <PokemonData 
            v-for="pokemon in pokemon" 
            :key="pokemon.id"
            :id="pokemon.id"
            :name="pokemon.name" 
            :type="pokemon.type"
            :pid="pokemon.pid"
            :isVisible="pokemon.isVisible"
            :rate="pokemon.rate"
            :img="pokemon.img"
            :info="pokemon.info"
            @addRate="plusRate"
            @downRate="minusRate"
            @showInfo="toggleVisible"
          />
      </ul>
    </div>
</template>

<script>
import PokemonData from './PokemonData.vue'

export default {
    name:"PokemonList",
    components: {
        PokemonData
    },
     data() {
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
    methods: {
        toggleVisible(id){
            this.pokemon = this.pokemon.map((eachItem)=>{
                if(eachItem.id === id){
                    return {...eachItem,isVisible:!eachItem.isVisible}
                }
                return eachItem
            })
        },
        plusRate(id){
            this.pokemon = this.pokemon.map((item)=>{
                if(item.id === id){
                    let currentRate = item.rate
                    if(currentRate < 5){
                        currentRate++
                    }else{
                        currentRate = 5
                    }
                    return {...item,rate:currentRate}
                }
                return item
            })
        },
        minusRate(id){
            this.pokemon = this.pokemon.map((item)=>{
                if(item.id === id){
                    let currentRate = item.rate
                    if(currentRate > 0 ){
                        currentRate--
                    } else {
                        currentRate = 0
                    }
                    return {...item,rate:currentRate}
                }
                return item
            })
        }
    },
}
</script>

<style scoped>
ul {
    list-style: none;
    margin: 1rem;
    padding: 0px;
}

</style>