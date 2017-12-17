<template>
    <div class="panel panel-default" @click="deleteQuote()">
        <div class="panel-body" @mouseover="active = !active" @mouseout="active = !active" :class="{'alert-danger': active}">
            {{entry}}
        </div>
    </div>
</template>

<script>
import { EventBus } from '../main';
export default {
  name: 'quote',
  props: ['entry'],
  data() {
      return {
          active: false
      }
  },
  computed: {
      mouseHover() {
          return 
      }
  },
  methods: {
      deleteQuote() {
          EventBus.$emit('deleteQuote', this.entry);
      },
      hoverClass() {
          console.log(this)
      }
  }
};
</script>

<style scoped>
    .panel-body {
        cursor: pointer;
    }

</style>


