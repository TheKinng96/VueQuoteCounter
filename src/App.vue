<template>
  <div class="container">
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-card :quotes="quotes"></app-quote-card>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on the card to delete it.</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteCard from "./components/QuoteCard.vue";
import NewQuote from "./components/NewQuote.vue";

export default {
  data: function () {
    return {
      quotes: ["The dummy string of quote"],
      maxQuote: 10,
    };
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    },
  },
  components: {
    appQuoteCard: QuoteCard,
    appNewQuote: NewQuote,
  },
};
</script>

<style></style>
