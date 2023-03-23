<template>
    <h1 :class="computedClass">{{count}}</h1>
    <button @click="clickFunction" >CLICK ME</button>
    <button @click="clickFunction2">CLICK ME to reduce</button>
</template>

<script>
// click => ++
// style binding

export default {
    name:"mainComp",
    data(){
        return {
            count : 1,
            secondCount: 1,
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
            // console.log("MY COMPUTED PROPERTY TRIGGERED")
            if(this.count % 2 === 0)
                return "red"
            else
                return "green"
        }
    },

    // create
    beforeCreate() {
        console.log("Before create", this.count)
    },
    created() {
        console.log("CREATED", this.count)
    },

    beforeMount() {
        console.log("Before mount", this.count)
    },
    mounted() {
        console.log("mounted", this.count)
    },

    beforeUpdate() {
        console.log("before update", this.count, this.secondCount)
    },
    updated() {
        console.log("updated", this.count, this.secondCount)
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
