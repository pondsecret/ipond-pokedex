<template>
    <div class="root-main">
        <div class="icon-container">
          <img src="https://img.icons8.com/color/48/000000/superball.png"/>
        </div>
        <li class="root">
            <h2 class="name-h2">Name: {{name}}</h2>
            <div class="type-container">
                <p>Type: {{type}} #{{pid}}</p>
            </div>
            <div class="rate-container">
                <button class="rate-btn" style="margin-right:10px" @click="downRate(id)">
                     <div class="inner-btn">-</div>
                </button>
                <ul>
                    <li v-for="(value) in rate" :key="value">
                        <img src="https://img.icons8.com/external-icongeek26-linear-colour-icongeek26/64/000000/external-star-origami-icongeek26-linear-colour-icongeek26.png" width="32" />
                    </li>
                </ul>
                <button class="rate-btn" @click="addRate(id)">
                    <div class="inner-btn">+</div>
                </button>
                <button class='toggle-btn' @click="showInfo(id)">{{isVisible ? 'Hide' : 'Show'}} Pokemon info</button>
            </div>
            <transition name="fade">
                <div class="pokemondata-container" v-show="isVisible" >
                    <div class="physicinfo-container">
                        <h2 class='info-topic'>Height</h2>
                        <h3 class='info-data'>{{info.height}} ft.</h3>
                        <h2 class='info-topic'>Weight</h2>
                        <h3 class='info-data'>{{info.weight}} lbs.</h3>
                        <h2 class='info-topic'>Gender</h2>
                        <h3 class='info-data'>{{info.gender}}</h3>
                    </div>
                    <div class="pokemon-img-container">
                        <img :src="img" width="350" >
                    </div>
                    <div class="otherinfo-container">
                        <h2 class='info-topic'>Ability</h2>
                        <ul>
                            <li v-for="(item,index) in info.ability" :key="index">
                                <h3 class='info-data'>{{item}}</h3>
                            </li>
                        </ul>
                        <h2 class='info-topic'>Weakness</h2>
                        <ul>
                            <li v-for="(item,index) in info.weakness" :key="index">
                                <h3 class='info-data'>{{item}}</h3>
                            </li>
                        </ul>
                    </div>
                </div>
            </transition>
        </li>
    </div>
</template>

<script>
export default {
    name: "PokemonData",
    data() {
        return {
        }
    },
    props: {
        id: {
            type: Number,
            required: true
        },
        name: {
            type: String,
            required: true
        },
        type: {
            type: String,
            required: true
        },
        pid: {
            type: Number,
            required: true
        },
        isVisible: {
            type: Boolean,
            required: true
        },
        rate:{
            type: Number,
            required: true
        },
        img:{
            type: String,
            required: true
        },
        info:{
            required: true
        }
    },
    computed: {
    },
    methods: {
        showInfo(id){
            // emit showInfo event with id param to Parent
            this.$emit("showInfo",id)
        },
        addRate(id){
            this.$emit("addRate",id)
        },
        downRate(id){
            this.$emit("downRate",id)
        },
    },
}
</script>

<style scoped>
.fade-enter-from{
    opacity: 0;
}
.fade-enter-active{
    transition: all 0.5s linear;
}
.rate-btn {
    cursor: pointer;
    margin: 0px 10px 0px 0px;
    padding: .2rem .2rem;
    background-color: transparent;
    border-radius: 8px;
    border:3px solid transparent;
}
.rate-btn:hover {
    border:2px solid rgba(0,0,0,0.5);
}
.inner-btn {
    display:flex;
    justify-content: center;
    align-items: center;
    background-color: #fff;
    width: 1.4rem;
    height: 1.25rem;
    font-size: 1.7rem;
    box-shadow: 0px 1px 3px rgba(33, 33, 33, 0.5);
    border-radius: 5px;
}
.root-main {
    box-shadow: 0 2px 8px rgba(145,145,145,0.5);
    padding: 1rem;
    border-radius: 3rem;
    margin-bottom: 2rem;
    margin-top: 2rem;
    display: flex;
    border:5px solid #000;
    padding: 2rem;
    background: linear-gradient(180deg ,#FFDE00 50%,#000 10%,#FFFFFF 55%);
}
.icon-container {
    margin-top: -15px;
}
.root {
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    display: flexbox;
    justify-content: center;
    align-items: center;
    color: #0C3348;
}
.name-h2{
    margin-top:-15px;
    margin-left: -120px ;
}
.rate-container {
    display: flex;
    justify-content: center;
    align-items: center;
}
.rate-container ul {
    list-style: none;
    margin-left: 0px;
    margin-right: 10px;
    padding: 0px;
}
.rate-container li {
    display: inline-block;
}
.toggle-btn {
    margin: 0px 10px 0px 20px;
    padding:6px 15px;
    font-size: 1rem;
    cursor: pointer;
    background-color: transparent;
    position: relative;
    border-color: transparent;
    transition: all 0.25s ease;
    color: white;
    overflow: hidden;
    border-radius: 20px;
    border-width: 0;
    box-shadow: 0px -0px 0px 0px rgba(223, 223, 223, 0.5),
        0px 0px 0px 0px rgba(251, 27, 27, 0.5);
}
.toggle-btn:hover {
   transform: translate(0, -3px);
    box-shadow: 3px -3px 7px 0px rgba(223, 223, 223, 0.5),
    -3px 3px 7px 0px rgba(251, 27, 27, 0.5);
}
.toggle-btn:hover::after {
  transform: rotate(150deg);
}
.toggle-btn::after{
  content: "";
  width: 400px;
  height: 400px;
  position: absolute;
  top: -50px;
  left: -100px;    
  background-color: #ff3cac;
  background-image: linear-gradient(255deg, #FB1B1B 0%,  #FB1B1B 50%,#DFDFDF 75% ,#000000 100%);
  z-index: -1;
  transition: all 0.25s ease;
}
.type-container p{
    font-size: 20px;
    font-weight: 600;
    color: #0A285F;
    margin-top: -10px;
    padding-bottom: 1rem;
    margin-left: -120px;
}
.pokemondata-container{
    display:inline-flex;
    justify-content: center;
    align-items: center;
}
.physicinfo-container {
    display: flexbox;
    text-align: left;
    padding: 1rem 2rem;
    border-radius: 6rem;
    border: 5px solid ;
    margin-left: -4rem;
    box-shadow: 0px 5px 20px rgba(145,145,145,0.5);
    background: linear-gradient(180deg ,#738bcd 50%,#000 1%,#FFFFFF 52%);
}
.physicinfo-container h3{
    margin-left: 30px;
}
.otherinfo-container {
    display: flexbox;
    text-align: left;
    padding: 1rem 2rem;
    border-radius: 6rem;
    border: 5px solid ;
    box-shadow: 0px 5px 20px rgba(145,145,145,0.5);
    background: linear-gradient(180deg ,#ff736a 50%,#000 1%,#FFFFFF 52%);
}
.otherinfo-container li{
    list-style: none;
}
.pokemon-img-container{
    padding: 2rem;
}
</style>