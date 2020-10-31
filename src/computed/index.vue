<template>
  <div class="container">
      <div class="jumbotron bg-dark text-center">
        <h1 class=" text-white">Computed</h1>
      </div>
      <div class="row">
        <div class="col-sm-6">
            <h2>Computed: {{counter}} {{compare}}</h2>
            <h2>Methods:  {{secondCounter}} {{result()}}</h2>
            <button class="btn btn-success mr-2" @click="counter++">Computed</button>
            <button class="btn btn-primary" @click="secondCounter++">Methods</button>
        </div>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            counter: 0,
            secondCounter: 0
        }
    },
    methods: {
        result() {
            console.log("result")
            return this.secondCounter > 5 ? "> 5" : "< 5"
        }
    },
    computed: {
        compare() {
            console.log("compare")
            return this.counter > 5 ? "> 5" : "< 5"
        }
    },
    watch: {
        counter() {
            setTimeout(() => {
                this.counter = 0
            },2000)
        }
    }
}
</script>

<style>

</style>