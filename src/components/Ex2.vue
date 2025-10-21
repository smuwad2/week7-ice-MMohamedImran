<script>
import { arrayBuffer } from 'stream/consumers';

    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter']
            }
            
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
     <ul id="listt">
        <li v-for="(item, index) in items"> 
            {{ item }} <button id="del" v-on:click="items.splice(1, index)"> delete </button>
        </li>
     </ul>
     
     <input type="text"><button id="add"> Add </button>
</template>
