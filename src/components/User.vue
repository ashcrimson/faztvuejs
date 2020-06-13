<template>
    <div class="users">
        <h1>User component</h1>
        <ul>
            <li v-for="user in user">
                {{user.name}} - {{user.email}} 
                <button v-on:click="deleteUser(user)">X</button>
            </li>
        </ul>
        <form v-on:submit.prevent="addUser">
            <input type="text" v-model="newUser.name" placeholder="Name">
            <input type="email" v-model="newUser.email" placeholder="Email">
            <button type="submit">
                Add
            </button>
        </form>
    </div>
</template>

<script>
export default {
    data(){
        return{
            user:[
            ],
            newUser:{
                
            }
        }
    },
    methods:{
        addUser(e){
            this.user.push(this.newUser);
            this.newUser = {};
        },
        deleteUser(user){
            this.user.splice(this.user.indexOf(user), 1);
        }
    },
    created(){
        this.$http.get('https://jsonplaceholder.typicode.com/users')
        .then(res=>this.user=res.body);
    }
}
</script>

<style>
    .users{
        background: #333;
        color: #fff;
        padding: 20px;
    }
</style>