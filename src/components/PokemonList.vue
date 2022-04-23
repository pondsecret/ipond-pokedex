<template>
  <div>
      <ul>
          <PokemonData 
            v-for="(pokemon,index) in pokemon" 
            :key="index"
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
            pokemon: this.pokemons
        }
    },
    props:{
        pokemons: {
            type: Array,
            required: true
        }
    },
    methods: {
        toggleVisible(id){
            this.pokemon = this.pokemon.map((eachItem)=>{
                console.log(id)
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