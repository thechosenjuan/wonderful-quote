<template>
  <div class="row">
    <div v-for="quote in quotesArray">
        <div class="col-md-4">
            <quote :entry="quote"></quote>
        </div>
    </div>
  </div>
</template>

<script>
import { EventBus } from '../main';
import Quote from './Quote';
export default {
  name: 'quotes',
  components: {
    Quote,
  },
  data() {
    return {
      quotesArray: [],
      newEntry: '',
    };
  },
  created() {
    EventBus.$on('registerQuote', entry => {
      if(this.quotesArray.length < 10) {
        this.quotesArray.push(entry);
        EventBus.$emit('changeQuoteArray', this.quotesArray);
      } else {
        alert('Max number of quotes reached')
      }
      
    });
    EventBus.$on('deleteQuote', entry => {
      let index = this.quotesArray.indexOf(entry);
      this.quotesArray.splice(index, 1)
      EventBus.$emit('changeQuoteArray', this.quotesArray);
    })
  },
};
</script>

<style scoped>
</style>


