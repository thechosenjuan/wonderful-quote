<template>
    <div>
        <h2>Quotes Added</h2>
        <div class="progress">
            <div class="progress-bar" role="progressbar" aria-valuenow="0" aria-valuemin="0" aria-valuemax="100" :style="{width: amountOfQuotes*10 + '%'}">
                {{amountOfQuotes}} / 10
            </div>
        </div>
    </div>
</template>

<script>
import { EventBus } from '../main';
export default {
  name: 'progressBar',
  data() {
      return {
          amountOfQuotes: 0
      }
  },
  created() {
      EventBus.$on('changeQuoteArray', array => {
          this.amountOfQuotes = array.length
      })
  }
};
</script>

<style scoped>
.progress {
  margin-top: 20px;
}
</style>


