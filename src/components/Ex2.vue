<script>
//import { arrayBuffer } from 'stream/consumers';

    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                addThis: ""
            }
            
        },
        //use method more accurate instead of computed when it is a function
        computed:{
            additem(){
                this.items.push(this.addThis)
            }
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
     <ul id="listt">
        <li v-for="(item, index) in items"> 
            {{ item }} <button id="del" v-on:click="items.splice(index, 1)" > delete </button>
        </li>
     </ul>
     
     <input id="it1" type="text" v-model="addThis"> <button id="add" v-on:click="additem()"> Add </button>
</template>
