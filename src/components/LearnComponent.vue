<template>
    <div>
        <p> <a v-bind:href="url" target="_blank">Google</a> </p>
        <h1>
            {{ fullname() }}
        </h1> 
        <hr />
        <p> age: {{ age }}</p>
        <label>First Name</label>
        <input type="text" v-model="firstName"/>
        <br/>
        
        <label>Last Name</label>
        <input type="text" :value="lastName" @input="updateLastName(`Last name trigered`, $event)"/>
        <br/>
        <button type="button" v-on:click="IncrementAge()">Increment</button> <br/>
        <button type="button" v-on:click="age--">Decrement</button>
        
        <br/>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                firstName: 'Hello',
                lastName: 'Tom',
                url: 'https://www.google.com',
                age: 10,
            };
        },

        methods: {
            fullname() {
                return `${this.firstName} ${this.lastName.toUpperCase()}`
            },
            IncrementAge() {
                this.age++;
            },
            mouseOver() {
                this.count++;
            },
            updateLastName(msg, event) {
                event.preventDefault();
                console.log(msg);
                this.lastName = event.target.value;
            }
        },


    }
</script>

<style scoped>
    h1 {
        color: red;
    }
    
</style>