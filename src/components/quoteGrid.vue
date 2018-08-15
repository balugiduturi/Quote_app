<template>
  <div class="row">
    <app-Quote v-for="(quote, index) in quotes" v-bind:key="index"  @click.native="deleteQuote(index)">{{quote}} -- {{index}}</app-Quote>
    
  </div>
</template>
<script>
import Quote from "./quote.vue";
export default {
  props: ["quotes"],
  components: {
    "app-Quote": Quote
  },
  methods: {
    deleteQuote: function(index) {
      this.$emit("emitDeleteQuote", index);
    }
  }
};
</script>
<style>
</style>
