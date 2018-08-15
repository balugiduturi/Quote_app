<template>
    <div class="container">
        <app-header :quotes="quotesList"></app-header>
        <app-new-quote-add @AddNewQuote="NewQuoteListen"></app-new-quote-add>
        <app-quoteGrid :quotes="quotesList" @emitDeleteQuote="listenDeleteQuote" ></app-quoteGrid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a quote to delete it!</div>
            </div>
        </div>
    </div>
</template>

<script>
  import quoteGrid from "./components/quoteGrid.vue";
  import NewQuoteAdd from "./components/newQuote.vue";
  import Header from "./components/Header.vue";

    export default {
        data:function(){
          return {
            quotesList : ["First quote", "Second quote","third quote"],
            maxQuotes : 10,
          }
        },
        methods:{
          NewQuoteListen : function(quote){
              this.quotesList.push(quote);
          },
          listenDeleteQuote : function(quoteIndex){
            this.quotesList.splice(quoteIndex,1);
          }
        },
        components:{
            "app-quoteGrid":quoteGrid,
            "app-new-quote-add" : NewQuoteAdd,
            "app-header" : Header
        }
    }
</script>

<style>
</style>
