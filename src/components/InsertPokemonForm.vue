<template>
    <div class="root-ctn">
        <form>
            <div class="content-ctn">
                <div class="inner-ctn">
                    <label for="pokemon-name">Pokemon Name :</label>
                    <input type="text" v-model="input.name">
                </div>
            </div>
            <div class="content-ctn">
                <div class="inner-two-ctn">
                    <div class="minor-ctn">
                        <label for="pokemon-type">Pokemon Type :</label>
                        <select v-model="input.type">
                            <option v-for="(item,index) in types" :key="index">{{item}}</option>
                        </select>
                    </div>
                     <div class="minor-ctn">
                        <label for="pokemon-pid">Pokedex Id :</label>
                        <input type="number" v-model="input.pid">
                    </div>
                </div>
            </div>
            <div class="content-ctn">
                <div class="inner-two-ctn">
                    <div class="minor-ctn">
                        <label for="pokemon-height">Height :</label>
                        <input type="number" v-model="input.height">
                    </div>
                     <div class="minor-ctn">
                        <label for="pokemon-weight">Weight :</label>
                        <input type="number" v-model="input.weight">
                    </div>
                </div>
            </div>
            <div class="content-ctn">
                <div class="inner-ctn">
                    <label for="pokemon-gender">Gender :</label>
                    <input type="text" v-model="input.gender">
                </div>
            </div>
            <div class="content-ctn">
                <div class="inner-ctn">
                    <label for="pokemon-image">Image Url :</label>
                    <input type="text" v-model="input.image_url">
                </div>
            </div>
            <div class="content-ctn">
                <div class="inner-ctn">
                    <label for="pokemon-ability">Ability :</label>
                    <ul>
                        <li v-for="(index) in abilityElements" :key="index">
                            <input type="text" v-model="input.abilities[index]">
                        </li>
                    </ul>
                </div>
            </div>
            <div class="content-ctn">
                <div class="button-ctn">
                    <button class="btn button--more" @click.prevent="addAbilityElement()"><span>More</span></button>
                    <button class="btn button--delete" @click.prevent="removeAbilityElement()" ><span>Delete</span></button>
                </div>
            </div>
            <div class="content-ctn">
                <div class="inner-ctn">
                    <label for="pokemon-weakness">Weakness :</label>
                    <ul class="inner-ul">
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[0]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[0]}">{{types[0]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[1]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[1]}">{{types[1]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[2]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[2]}">{{types[2]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[3]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[3]}">{{types[3]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[4]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[4]}">{{types[4]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[5]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[5]}">{{types[5]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[6]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[6]}">{{types[6]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[7]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[7]}">{{types[7]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[8]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[8]}">{{types[8]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[9]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[9]}">{{types[9]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[10]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[10]}">{{types[10]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[11]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[11]}">{{types[11]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[12]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[12]}">{{types[12]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[13]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[13]}">{{types[13]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[14]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[14]}">{{types[14]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[15]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[15]}">{{types[15]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[16]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[16]}">{{types[16]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[17]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[17]}">{{types[17]}}</label>
                                </div>
                            </div>
                        </li>  
                        <li class='inner-li'>
                            <div class="li-ctn">
                                <div>
                                    <input type="checkbox" v-model="input.weakness" :value="types[18]">
                                    <label for="pokemon-weakness-type" v-bind:style="{color:type_colors[18]}">{{types[18]}}</label>
                                </div>
                            </div>
                        </li>                           
                    </ul>
                </div>
            </div>
            <div class="content-ctn">
                <div class="button-ctn">
                    <button class="button button--dione" @click.prevent="saveForm()"><span>Save</span></button>
                </div>
            </div>
        </form>
    </div>
</template>

<script>

export default {
    name: "InsertPokemonForm",
    data() {
        return {
            types: ['Normal','Fire','Fighting','Water','Flying','Grass','Poison','Electric','Ground','Physic','Rock','Ics','Bug','Dragon','Ghost',
            'Dark','Steel','Fairy','Unknown'],
            type_colors:['#a8a878','#f08030','#c84d47','#6890f0','#a890f0','#78c850','#a040a0','#efcf53','#e0c068','#f85888','#b8a038','#98d8d8','#a8b820',
            '#7038f8','#705898','#000','#b8b8d0','#f0b6bc','#6da899'],
            input:{
                name:'',
                type:'Normal',
                pid: 0,
                height: 0,
                weight: 0,
                gender: '',
                image_url: '',
                abilities:[],
                weakness:[],
            },
            abilityElements: [0],
            weaknessElements: [0],
        }
    },
    methods:{
        addAbilityElement(){
            return this.abilityElements.push(this.abilityElements.length) 
        },
        removeAbilityElement(){
            return this.abilityElements.pop()
        },
        saveForm(){
            this.$emit("onSaved",this.input)
        }
    },
}
</script>

<style scoped>

form{
    margin:2rem auto;
    max-width: 40rem;
    border-radius: 12px;
    box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.25);
    padding: 1rem;
    background: #fff;
    display: flexbox;
    justify-content: left;
    text-align: left;
}
.inner-ul{
    display: grid;
    grid-template-columns: auto auto auto auto;
}
.inner-li {
    list-style-type: none;
}

.li-ctn input[type="checkbox"]{
    display: inline-block;
    width: auto;
    margin: 1rem;
}

.content-ctn {
    background: transparent;
    margin: 1rem 1.5rem;
    padding: 0rem;
}
.inner-ctn input{
    display: block;
    margin-top: 1rem ;
    width: 99%;
    padding: 3px  0px;
    font:inherit;
    border-top-color: transparent;
    border-left-color: transparent;
    border-right-color: transparent;
    border-bottom-color: #ababab;
    outline: none;
    border-radius: 5px ;
}
.inner-ctn input[type="text"]:focus,input[type="number"]:focus {
    border-bottom-color: rgb(62, 182, 182);
    border-bottom-width: 3px;
    border-right-color: rgb(62, 182, 182);
    border-right-width: 2px;
    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.25);
}
.inner-ctn label{
    font-weight: bold;
    margin-bottom: 1rem;
    color: #727171
}

.inner-two-ctn {
    display: flex;
    justify-content: space-between;
}
.minor-ctn {
    width: 48%;
}
.minor-ctn input,select{
    display: flex;
    width: 97%;
    padding: 3px  0px;
    font:inherit;
    border-top-color: transparent;
    border-left-color: transparent;
    border-right-color: transparent;
    border-bottom-color: #ababab;
    outline: none;
    border-radius: 5px ;
    margin-top: 1rem;
}
.minor-ctn input[type="text"]:focus,input[type="number"]:focus,select:focus{
    border-bottom-color: rgb(62, 182, 182);
    border-bottom-width: 3px;
    border-right-color: rgb(62, 182, 182);
    border-right-width: 2px;
    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.25);
}
.minor-ctn label{
    font-weight: bold;
    color: #727171
}
.button-ctn {
    display: flex;
    justify-content: right;
    align-items: center;
}
.button {
	pointer-events: auto;
	cursor: pointer;
	background: #fff;
	border: none;
	padding: .7rem 1.3rem;
    width: 100%;
	margin: 0;
	font-family: inherit;
	font-size: inherit;
	position: relative;
	display: inline-block;
}

.button::before,
.button::after {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}

.button--dione span {
	display: inline-block;
	position: relative;
	color: #fff;
}

.button--dione::before {
	content: '';
	background: #5999E5;
	transition: transform 0.3s cubic-bezier(0.2,1,0.7,1);
    border-radius: 8px ;
    box-shadow: 0 2px 8px rgba(145,145,145,0.5)
}

.button--dione:hover::before {
    background: #007DFF;
	transform: scale3d(0.98, 0.8, 1);
}

.button--dione::after {
	content: '';
	border: 1px solid #5999E5;
	transition: transform 0.3s cubic-bezier(0.2,1,0.7,1);
	border-radius: 10px;
	transform: scale3d(0.85, 0.65, 1);
}

.button--dione:hover::after {
	transform: scale3d(1,1,1);
}
li {
    list-style-type: decimal;
}

/* More button */
.btn {
	pointer-events: auto;
	cursor: pointer;
	background: #fff;
	border: none;
	padding: .5rem 1.1rem;
	margin: 0;
	font-family: inherit;
	font-size: inherit;
	position: relative;
	display: inline-block;
}

.btn::before,
.btn::after {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
.button--more span {
	display: inline-block;
	position: relative;
	color: #fff;
    font-size: 15px;
}
.button--more{
    margin-right: .5rem;
}
.button--more::before {
	content: '';
	background: #5999E5;
	transition: transform 0.3s cubic-bezier(0.2,1,0.7,1);
    border-radius: 8px ;
    box-shadow: 0 2px 8px rgba(145,145,145,0.5)
}

.button--more:hover::before {
    background: #007DFF;
	transform: scale3d(0.9, 0.75, 1);
}

.button--more::after {
	content: '';
	border: 1px solid #5999E5;
	transition: transform 0.3s cubic-bezier(0.2,1,0.7,1);
	border-radius: 10px;
	transform: scale3d(0.85, 0.65, 1);
}

.button--more:hover::after {
	transform: scale3d(1,1,1);
}
/* Delete button */
.button--delete span {
	display: inline-block;
	position: relative;
	color: #fff;
    font-size: 15px;
}

.button--delete::before {
	content: '';
	background: #fc4242;
	transition: transform 0.3s cubic-bezier(0.2,1,0.7,1);
    border-radius: 8px ;
    box-shadow: 0 2px 8px rgba(145,145,145,0.5)
}

.button--delete:hover::before {
    background: red;
	transform: scale3d(0.9, 0.75, 1);
}

.button--delete::after {
	content: '';
	border: 1px solid #fc4242;
	transition: transform 0.3s cubic-bezier(0.2,1,0.7,1);
	border-radius: 10px;
	transform: scale3d(0.85, 0.65, 1);
}

.button--delete:hover::after {
	transform: scale3d(1,1,1);
}
</style>