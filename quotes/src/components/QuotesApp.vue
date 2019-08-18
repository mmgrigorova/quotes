<template>
  <div class="container ">

    <app-header :quotesCount="quotes.length"
                :maxQuotes="maxQuotes"></app-header>
    <hr>
    <add-quote :quotesCount="quotes.length" :maxQuotes="maxQuotes"
               @quoteAdded="addQuote"></add-quote>
    <hr>
    <quotes-list :quotes="quotes"
                 @quoteDeleted="deleteQuote"></quotes-list>
  </div>
</template>

<script>
  import QuotesApp from './QuotesApp'
  import AddQuote from './AddQuote'
  import QuotesList from './QuotesList'
  import Header from './Header';

  export default {
    name: "QuotesApp",
    data() {
      return {
        title: "Quotes Added",
        quotes: [],
        maxQuotes: 10
      }
    },
    components: {
      QuotesApp,
      'appHeader': Header,
      AddQuote,
      QuotesList
    },
    methods: {
      addQuote(quote) {
        if (this.quotes.length < 10) {
          this.quotes.push(quote);
        }
      },
      deleteQuote(index) {
        this.quotes.splice(index, 1);
      }
    }
  }
</script>

<style>

</style>
