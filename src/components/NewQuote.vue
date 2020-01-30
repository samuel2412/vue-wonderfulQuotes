<template>
  <div class="container">
    <div class="row">
      <label>Quote</label>
      <textarea v-model="quote" @keydown.enter="newQuote" class="form-control" rows="3"></textarea>
      <button
        @click="newQuote"
        v-if="quotesSize<maxQuotes"
        class="btn btn-primary"
        style=" margin: 30px auto;"
      >Add Quote</button>
      <div
        v-else
        class="alert alert-warning"
        role="alert"
      >You can't add more than {{maxQuote}} quotes.</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["addQuote", "maxQuotes", "quotesSize"],
  data: function(){
    return{
      quote: '',
    }
  },
  methods: {
    newQuote() {
      this.addQuote(this.quote);
      this.quote = "";
    }
  }
};
</script>

<style scoped>
</style>