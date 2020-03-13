<template>
  <div id="app">
    <div class ="XaO">
      <div class = "column" v-for="i in 3" :key = "i">
        <div class="row" @click="clickCell"></div>
        <div class="row" @click="clickCell"></div>
        <div class="row" @click="clickCell"></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        is_x: true
      }
    },
    methods:{
      clickCell (e) {

        if (e.target.innerText) {
          return 1
        }

        if(this.$data.is_x) {
          e.target.innerText = "x"
        } else {
          e.target.innerText = "o"
        }

        this.$data.is_x = !this.$data.is_x

        return 1
      }
    }

  }
</script>

<style lang="scss">
#app {
  margin: auto;

  .XaO {
    
    width: 200px;
    height: 200px;

    display: grid;
    grid-template-rows: 1fr 1fr 1fr ;
  }

  .column {
    border: 1px solid black;
    background:rgb(173, 150, 238);
    position: relative;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr ;


    .row {
      border: 1px solid black;
      height: 100% ;
      text-align: center;
    }

  }

}


</style>
