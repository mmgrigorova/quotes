<template>
  <div class="container">
    <div v-if="quotes.length === 0">
      <div class="col-sm alert alert-primary">Add your first quote!</div>
    </div>
    <div v-else="">
      <!--      <button @click="deleteQuote">Delete Quote</button>-->
      <div class="row">
        <quote v-for="(quote, index) in quotes" class="quotes"
               :key="index"
               @click.native="deleteQuote(index)">
          {{ quote }}
        </quote>
      </div>
      <div class="row">
        <div class="col-sm-12 alert alert-primary remove-msg">Click on Quote to delete it</div>
      </div>
    </div>
  </div>
</template>

<script>
  import Quote from './Quote';

  export default {
    name: "QuotesList",
    components: {
      Quote
    },
    props: {
      quotes: Array
    },
    methods: {
      deleteQuote(index) {
        this.$emit("quoteDeleted", index);
      }
    }
  }
</script>

<style scoped>
  .remove-msg{
    margin-top: 10px;
  }
</style>
