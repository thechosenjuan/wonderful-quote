<template>
    <div class="quote-entry">
        <h4>Quote</h4>
        <div class="input-group">
            <textarea name="" id="" class="entry-textarea" placeholder="Add a new quote" v-model="entry" rows="10" cols="70"></textarea>
        </div>
        <button class="btn btn-primary" @click="newQuote()">Add Quote</button>
    </div>
</template>

<script>
import Quotes from './Quotes';
import { EventBus } from '../main';
export default {
  name: 'quoteEntry',
  components: {
    Quotes,
  },
  data() {
    return {
      entry: '',
    };
  },
  methods: {
    newQuote() {
      if(this.entry != '') {
        EventBus.$emit('registerQuote', this.entry);
        this.entry = '';
      }
    },
  },
};
</script>

<style scoped>
button {
  margin-bottom: 15px;
}
</style>

