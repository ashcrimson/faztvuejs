<template>
    <div class="test">
        {{msg}}
    </div>
</template>

<script>
export default {  
    data(){
        return{
            title:'Hola Vuejs',
            user:{
                firstName: 'Joe',
                lastName: 'McMillan'
            },
            myHtml: '<h3>hola vue</h3>',
            showName: false,
            tasks:[
                {title: 'eat'},
                {title: 'dinner'},
                {title: 'play'},
                {title: 'tasks'}
            ]
        }
    },
    methods:{
        saludar(name){
            alert('hello' + name)
        },
        typedEnter(e){
            console.log('Dió un enter');
            
        }
    },
    computed:{
        fullName(){
            return this.user.firstName + ' ' + this.user.lastName;
        }
    },
    props:{
        msg:{
            type:String,
            default:'Mensaje por defecto'
        }
    }
}
</script>
<style>
.test{
    background-color: #eee;
}
</style>