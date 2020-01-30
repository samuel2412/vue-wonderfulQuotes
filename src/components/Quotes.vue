<template>
  <div class="row">
      <app-quote  v-for="(quote,index) in quotes" :key="index" @click.native="removeQuote(index)">
         
            {{quote}}
         
      </app-quote>
  </div>
</template>

<script>
import Quote from './Quote.vue';
export default {
  props: ["quotes","removeQuote"],

  components:{
      appQuote: Quote,
  }

};
</script>

<style scoped>
</style>