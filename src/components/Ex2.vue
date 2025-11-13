<script>
    export default { 
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                newItem: ''
            }
        },
        methods: {
            add() {
                // console.log('in add')
                this.items.push(this.newItem)
                this.newItem = ''
            }
        }
    }
</script>

<template>
    <h2>Shopping Cart</h2>
    <ul>
        <li v-for="(item, i) in items">
            {{item}}
        <button @click="items.splice(i, 1)">Delete!</button> </li>
    </ul>
    <input @keyup.enter="add" v-model="newItem"/>
    <button @click="add">Add!</button>    
   
</template>