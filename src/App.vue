<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-card
      :quotes="quotes"
      @quoteDeleted="deleteQuote"
    ></app-quote-card>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Info: Click on the memo card to delete it.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteCard from "./components/QuoteCard.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data: function() {
    return {
      quotes: [],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please delete Quotes first");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  },
  components: {
    appQuoteCard: QuoteCard,
    appNewQuote: NewQuote,
    appHeader: Header
  }
};
</script>

<style></style>
