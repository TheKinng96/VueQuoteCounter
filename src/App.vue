<template>
  <div class="container">
    <app-quote-card :quotes="quotes"></app-quote-card>
  </div>
</template>

<script>
import QuoteCard from "./components/QuoteCard.vue";

export default {
  data: function () {
    return {
      quotes: ["The dummy string of quote"],
      maxQuote: 10,
    };
  },
  components: {
    appQuoteCard: QuoteCard,
  },
};
</script>

<style></style>
