<template>
  <div class="container">
      <div class="jumbotron bg-dark text-center">
        <h1 class=" text-white">Directive</h1>
      </div>
      <div class="row">
        <div class="col-sm-6">
           <div v-if="status">CYBERSOFT</div>
           <div v-else>NTP</div>
           <button class="btn btn-success" @click="status = !status">Toggle</button>
           <hr/>
           <div v-show="show">v -show</div>
            <table class="table table-bordered">
                <thead>
                    <tr>
                        <th>Id</th>
                        <th>Name</th>
                        <th>Age</th>
                        <th>Color</th>
                    </tr>
                </thead>
                <tbody>
                    
                    <tr v-for="(item, index) in persons" :key="index">
                        <td>{{index + 1}}</td>
                        <td>{{item.name}}</td>
                        <td>{{item.age}}</td>
                        <td :style="{'background-color': item.color}">{{item.color}}</td>
                    </tr>
                </tbody>
            </table>

            <div v-for="(value, key, index) in people" :key="key">{{index}} {{key}} {{value}}</div>
            <div class="flex">
                <div class="demo m-2" :class="divClass" @click="statusClass = !statusClass"></div>


            <div class="demo m-2" :class="[activeClass, textDangerClass]">CyberSoft</div>
            </div>

        </div>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
           status: true,
           statusClass: false,
           show: true,
           persons: [
               {
                   name: "cybersoft",
                   age: 100,
                   color: "violet"
               },
               {
                   name: "BBB",
                   age: 98,
                   color: "red"
               },
               {
                   name: "AAA",
                   age: 100,
                   color: "aqua"
               },
           ],
           people: {
               name: "cybersoft",
               age: 100,
               color: "violet"
           },
           activeClass: "active",
           textDangerClass: "text-danger"
        }
    },
    computed: {
        divClass() {
            return {
                red: this.statusClass,
                //text: this.statusClass
            }
        }
    }
}
</script>

<style>
    .red {
        background-color: red !important;
    }
    .demo {
        width: 100px;
        height: 100px;
        background-color: purple;
    }
    .active {
        background-color: lime;
    }
    .text-danger {
        color: red;
    }
    .flex {
        display: flex;
    }
</style>