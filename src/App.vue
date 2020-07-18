<template>
    <div class="container">
      <app-new-quote @addQuote="pushQuote($event)"></app-new-quote>
      <app-quote-grid v-bind:quotes='quotes' @deleteQuoted='deleteQuote'></app-quote-grid>
      <div class="row">
        <div class="alert alert-danger col-sm-12 text-center mt-3 alert-dismissible fade show" role="alert" v-if="shart">
          Enter text please !
          <button class="close" data-dismiss="alert" aria-label="Close" @click="shart = false">
            <i aria-hidden="true">&times;</i>
          </button>
        </div>
        <div class="alert alert-info col-sm-12 text-center mt-3">
          Info: Clickon a Quote to delete it !
        </div>
        
      </div>
    </div>
</template>

<script>
  import QuoteGrid from './component/QuoteGrid'
import NewQuote from './component/NewQuote'
  
  export default {
    data: function(){
      return{
        quotes: ['Just a Quote to see something'],
        maxQuotes: 10,
        shart: false
      }
    },
    components: {
      appQuoteGrid:QuoteGrid,
      appNewQuote: NewQuote
    },
    methods:{
      pushQuote: function(quote){
        if(quote !== ''){
          this.quotes.push(quote);
          this.shart = false;

        }else{
          this.shart = true;
        }
      },
      deleteQuote(index){
        this.quotes.splice(index, 1);
      }
    }
  }
</script>

<style lang="scss" scoped>
  .container{
    margin:100px auto;
    background:rgba(185, 185, 78, .2);
    padding:20px 50px;
  }
</style>