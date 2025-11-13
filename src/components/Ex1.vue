<script>
    export default { 
        data() {
            return { 
                x: 0, 
                y: 0, 
                lastResult: 0,
                operators: ["+", "-", "*", "/", "%"],
                selectedOp: "+"
            }
        },
        computed: {
            result() {
                if (this.selectedOp == "+")
                    this.lastResult = this.x + this.y;
                else if (this.selectedOp == "-")
                    this.lastResult = this.x - this.y;
                else if (this.selectedOp == "*")
                    this.lastResult = this.x * this.y;
                else if (this.selectedOp == "/")
                    this.lastResult = this.x / this.y;
                else if (this.selectedOp == "%")
                    this.lastResult = this.x % this.y;

                return this.lastResult;
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