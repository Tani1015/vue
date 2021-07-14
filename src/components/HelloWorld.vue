<template>
  <div>
    {{ message }}
    <button @click="this.test">test</button>
  </div>
</template>

<script>
import axios from "axios"

export default {
  name: 'HelloWorld',
  data:()=>{
    return{
      message: 'Hello Vue!'
    }
  },
  methods: {
    test(){
      axios
        .get('http://test/school/')
        .then( response =>{
            this.message = response
        })
        .catch(error => {
            console.log(error);
        });
    }
  }
}
</script>
