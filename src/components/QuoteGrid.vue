<template lang="html">
  <div class="row">
    <app-quote v-for="(quote, index) in quotes" @click.native="removeQuote(index)">{{quote}}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue"

export default {
  props: ['quotes'],
  components: {
    appQuote: Quote
  },
  methods: {
    removeQuote: function(index){
      this.$emit('removeQuote', index)
    }
  }
}
</script>

<style lang="css">
</style>
