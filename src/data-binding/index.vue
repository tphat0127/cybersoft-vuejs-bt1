<template>
  <div class="container">
      <div class="jumbotron bg-dark text-center">
        <h1 class=" text-white">Data-binding</h1>
      </div>
      <!-- <p class="">{{userName}}</p>
      <img :src="imgUrl" />
      <p v-html="rawHTML"></p> -->
      <div class="row">
        <div class="col-sm-6">
          <div class="form-group">
            <label for="">Email</label>
            <input type="text" name="" id="" class="form-control" v-model="email">
          </div>

          <div class="form-group">
            <label for="">Full name</label>
            <input type="text" name="" id="" class="form-control" ref="txtFullName">
          </div>
          <button class="btn btn-success" v-on:click="eventBinding($refs.txtFullName.value)">Click</button>
        </div>
      </div>
      <p>Email: {{email}}</p>
      <p>Full Name: {{fullName}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      fullName: ""
    }
  },
  methods: {
    eventBinding(value) {
      this.fullName = value
    }
  }
}
</script>

<style>

</style>