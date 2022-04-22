<template>
    <div class="root">
        <div class="button-root-ctn">
            <button class="button button--dione" @click="showFormToggle()">
                <span>{{showForm ? 'Hide Form' : 'Add Pokemon' }}</span>
            </button>
        </div>
        <transition name="fade">
            <InsertPokemonForm v-show="showForm"/>
        </transition>
        
    </div>
</template>

<script>
import InsertPokemonForm from './InsertPokemonForm.vue'
export default {
    name:'FormTemplate',
    components :{
        InsertPokemonForm
    },
    data() {
        return {
            showForm: false
        }
    },
    methods:{
        showFormToggle(){
            return this.showForm = !this.showForm
        }
    },
}
</script>

<style scoped>
.root {
    display: flexbox;
    justify-content: right;
    margin:  2rem 6rem;
}
.fade-enter-from{
    opacity: 0;
}
.fade-enter-active{
    transition: all 0.5s linear;
}
.button-root-ctn
{
    display: flex;
    justify-content: right;
}
.button {
	pointer-events: auto;
	cursor: pointer;
	background: #fff;
	border: none;
	padding: 1rem 2rem;
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
	background: #4dad7d;
	transition: transform 0.3s cubic-bezier(0.2,1,0.7,1);
    border-radius: 8px ;
    box-shadow: 0 2px 8px rgba(145,145,145,0.5)
}

.button--dione:hover::before {
    background: #4e9c8e;
	transform: scale3d(0.9, 0.75, 1);
}

.button--dione::after {
	content: '';
	border: 1px solid #4dad7d;
	transition: transform 0.3s cubic-bezier(0.2,1,0.7,1);
	border-radius: 10px;
	transform: scale3d(0.85, 0.65, 1);
}

.button--dione:hover::after {
	transform: scale3d(1,1,1);
}
</style>