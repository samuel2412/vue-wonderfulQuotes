<template>
  <section>
    <h3>Quotes added</h3>
    <div class="progress" style="height: 30px">
      <div
        class="progress-bar"
        role="progressbar"
        :style="{width: (size/maxSize)*100 +'%'}"
        :aria-valuenow="size"
        aria-valuemin="0"
        :aria-valuemax="{maxSize}"
      >{{size}} / {{maxSize}}</div>
    </div>
  </section>
</template>

<script>
import { eventBus } from "../main";
export default {
  props: ['size','maxSize'],
    
};
</script>

<style scoped>
section {
  margin: 30px auto;
}
</style>