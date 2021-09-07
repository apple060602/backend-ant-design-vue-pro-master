<template lang="">

</template>

<script>
import axios from 'axios';
  axios.get('http://localhost:9000/transfers')
  .then(function(res){
    console.log(res)
  })

export default {
  
}
</script>

<style lang="">
  
</style>