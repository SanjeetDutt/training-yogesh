<template>
    <h1 :class="computedClass">{{count}}</h1>
    <button v-on:click="clickFunction">CLICK ME</button>
    <button v-on:click="clickFunction2">CLICK ME to reduce</button>
</template>

<script>
// click => ++
// style binding

export default {
    name:"mainComp",
    data(){
        return {
            count : 1,
        }
    },
    methods:{
        clickFunction(){
            this.count++;

        },
        clickFunction2(){
            this.count--;

        }
    },

    computed:{
        computedClass(){
            console.log("MY COMPUTED PROPERTY TRIGGERED")
            if(this.count % 2 === 0)
                return "red"
            else
                return "green"
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
