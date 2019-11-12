<template>
  <div class="about">
    <h1>{{returnValue}}</h1>
  </div>
</template>


<script>

import axios from "axios";
export default {
  data(){
    return{
      returnValue:''
    }
  },
  methods: {
      init: function(e) {
          axios.get("http://localhost:9000/wykd-user/userService/index").then(res => {
            console.log(res);
            alert(res.data);
            this.returnValue = res.data;
          });
      }
  },
  created:function(){
    this.init();
  }
}


</script>
