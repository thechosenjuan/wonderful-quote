<template>
  <div class="container">
    <progressBar></progressBar>
    <quoteEntry></quoteEntry>
    <quotes></quotes>
  </div>
</template>

<script>
import ProgressBar from './components/ProgressBar';
import QuoteEntry from './components/QuoteEntry';
import Quotes from './components/Quotes';
export default {
  components: {
    ProgressBar,
    QuoteEntry,
    Quotes,
  },
  data() {
    return {
      newQuote: '',
    };
  },
  methods: {
    registerQuote(entry) {
      this.newQuote = entry;
    },
  },
};
</script>

<style>

</style>
