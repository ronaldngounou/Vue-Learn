<template>
    <div>
        <h1>
            {{ fullname() }}
        </h1> 
        <hr />

        <label>First Name</label>
        <input type="text" v-model="firstName"/>
        <br/>
        
        <label>Last Name</label>
        <input type="text" v-model="lastName"/>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                firstName: 'Hello',
                lastName: 'Tom'
            };
        },

        methods: {
            fullname() {
                return `${this.firstName} ${this.lastName.toUpperCase()}`
            }
        },


    }
</script>

<style scoped>
    h1 {
        color: red;
    }
</style>