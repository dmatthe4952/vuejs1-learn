<template>
  <div class="row">
    <div class="progbar" :style='cBoxLength'>
      {{boxText}}
    </div>
  </div>

</template>
<script>
  export default{
    props:  ['quotes'],
    data: function(){
      return {
        boxlength: this.quotes.length
      }
    },
    computed: {
      cBoxLength: function(){
        return {width: this.boxlength * 10 + '%'}
      },
      boxText: function(){
        return this.boxlength + "/10"
      }
    }
  }
</script>
<style>
.progbar {
  background-color: blue;
  height: 20px;
  margin: 10px;
  color: white;
  text-align: center;
}

</style>
