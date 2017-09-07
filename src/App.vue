<template>
    <div class="container">
      <h2>Quotes added</h2>
      <div class="row">
        <prog-bar :quotes='quotes'></prog-bar>
      </div>
      <hr>
      <addQuote :quotes='quote' @quoteAdded="addQuote"></addQuote>
      <quote-grid :quotes='quotes' @removeQuote="removeQuote"></quote-grid>
      <div class="row">
        <div class="col-sm-12">
          <div class="alert alert-info text-center">Info: Click on a Quote to delete it.</div>
        </div>
      </div>
    </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid.vue';
  import ProgBar from './components/ProgBar.vue';
  import AddQuote from './components/AddQuote.vue'

  export default{
    data() {
      return {
        quotes: [
          'This is the first quote to see something.',
          'This is the second quote.',
          'This is the third quote.',
          'This is the fourth quote.',
          'This is the fifth quote.',
          'This is the sixth quote.'
        ],
        maxEntries: 10
      }
    },
    components: {
      'quoteGrid': QuoteGrid,
      'progBar': ProgBar,
      'addQuote': AddQuote
    },
    methods: {
      addQuote: function(quote){
        if (this.quotes.length == 10) {
          alert("Quotes page is full. \n You can not add more quotes.")
        }else{
          this.quotes.push(quote);
        }
      },
      removeQuote: function(index){
        console.log(index);
        this.$delete(this.quotes,index);
      }
    }
  }
</script>

<style scoped>
  div {

  }
</style>
