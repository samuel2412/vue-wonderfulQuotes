<template>
  <div class="container">
    <app-header :maxSize="maxQuotes" :size="quotes.length" ></app-header>
    <app-new-quote :maxQuotes="maxQuotes" :quotesSize="quotes.length" :addQuote="addQuote" ></app-new-quote>
    <app-quotes :quotes="quotes" :removeQuote="removeQuote"></app-quotes>

    <div
      class="alert alert-primary text-center"
      
      role="alert"
    >Click on a Quote to delete it!</div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import NewQuote from "./components/NewQuote.vue";
import Quotes from "./components/Quotes.vue";

export default {
  data: function() {
    return {
      quotes: [],
      maxQuotes: 10
    };
  },
  methods: {
    addQuote(quote) {
      this.quotes.push(quote)
    },
    removeQuote(index) {
      this.quotes.splice(index,1)
    }
  },
  components: {
    appHeader: Header,
    appNewQuote: NewQuote,
    appQuotes: Quotes
  }
};
</script>

<style>
body {
  background-color: #fcfcfc;
}
div .alert {
  margin: 30px auto;
}
</style>
