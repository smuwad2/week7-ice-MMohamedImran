<script>
    export default { 
        // Add Code Here to complete the task
        // Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!
        data(){
            return{
                x: "",
                y: "",
                operators: ["+", "-", "*", "/", "%"],
                selectedOp: ""
        }
    },
    computed: {
        result(){
            return this.x + this.selectedOp + this.y
        }
    }
    }
</script>

<template>
    <p>x <input v-model.number="x"></p>
    <select v-model="selectedOp">
        <option v-for="op in operators" >{{ op }}</option>
    </select>
    <p>y <input v-model.number="y"></p>
    
    <p>---------------------</p>

    <p>= {{result}}</p>
</template>

<style scoped>
    p, input { font-family: monospace; }
    p { white-space: pre; }

</style>
