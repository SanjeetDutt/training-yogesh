<template>
    <h1>Hello world !! {{name}}</h1>
    <h2>{{count}}</h2>

    <p v-html="text" :class="textClass"></p>

    <p v-bind="attrBind">This is a dynamic paragraph</p>

    <div></div>

    <ul>
        <li v-for="name in names">{{name}}</li>
    </ul>
</template>

<script>

export default {
    name:"mainComp",
    data(){
        return {
            count : 1,
            name:{
                fName: "sanjeet",
                lastName:"Dutt"
            },
            names:[
                "SANJEET","YOGESH","Srinivas"
            ],
            text:"<b>THis is error</b>",
            textClass:"green",

            attrBind:{
                class:"red",
                id:"my-dynamic-p",
                title:"my dynamic paragraph"
            }
        }
    },
    methods:{
        click(){
            alert("HELLO")
        }
    }


}
</script>

<style scoped>
.red{
    color: red;
}

.green{
    color: green;
}
</style>
