<template>
  <div class="container">
      <div class="">Exemple Directive</div>
      <div class="row">
          <div class="col-sm-8">
              <div class="form-group">
                <label for="">Id</label>
                <input type="text" name="" id="" class="form-control" ref="txtId">
              </div>
              <div class="form-group">
                <label for="">Name</label>
                <input type="text" name="" id="" class="form-control" ref="txtName">
              </div>
              <div class="form-group">
                <label for="">Price</label>
                <input type="text" name="" id="" class="form-control" ref="txtPrice">
              </div>
              <button class="btn btn-success" @click="addProduct(
                  $refs.txtId.value, 
                  $refs.txtName.value, 
                  $refs.txtPrice.value
                  )">Submit</button>
          </div>
          <table class="table mt-2">
              <thead>
                  <tr>
                      <th>Id</th>
                      <th>Name</th>
                      <th>Price</th>
                  </tr>
              </thead>
              <tbody>
                  <tr v-for="(item, index) in listProduct" :key="index">
                      <td>{{item.id}}</td>
                      <td>{{item.name}}</td>
                      <td>{{item.price}}</td>
                  </tr>
              </tbody>
          </table>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            listProduct: []
        }
    },
    methods: {
        addProduct(id, name, price) {
            const product = { id:id, name:name, price:price}
            console.log(product)
            this.listProduct.push(product)
        }
    }
}
</script>

<style>

</style>