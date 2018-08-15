<template>
<div class="row">
<div class="col-sm-12">
<h2>Quotes Added</h2>
<div class="progress">
  <div class="progress-bar" role="progressbar" aria-valuenow="70"
  aria-valuemin="0" aria-valuemax="10" :style="progress_bar_w"> 
    <span class="sr-only">70% Complete</span>
  </div>
</div>
</div>
</div>
</template>

<script>
export default {
  props: ["quotes"],
  data: function() {
    return {
      progress_bar_width: 0
    };
  },
  computed: {
    progress_bar_w: function() {
      let progres_bar = (this.quotes.length / 10) * 100;
      return "width:" + progres_bar + "%";
      // return (10 / 10) * 100;
    }
  }
};
</script>
