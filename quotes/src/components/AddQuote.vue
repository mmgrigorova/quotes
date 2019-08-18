<template>
  <div class="container">
    <div class="row  justify-content-md-center">
      <textarea class="col-sm-6 form-control" v-model="quote"
                placeholder="Put in a nice quote here!"
                name="addQuote"></textarea>
    </div>
    <div class="row justify-content-md-center">
      <button @click="addQuote(quote)" class="btn btn-primary" :disabled="quotesCount >= maxQuotes">Add Quote</button>
    </div>
  </div>
</template>

<script>
  export default {
    name: "AddQuote",
    props:['quotesCount', 'maxQuotes'],
    data() {
      return {
        quote: ""
      }
    },
    methods: {
      addQuote(quote) {
        this.$emit("quoteAdded", quote);
        this.quote = "";
      }
    }
  }
</script>

<style scoped>
  .btn{
    margin-top: 5px;
  }
</style>
