<template>
  <div class="HolyGrail" :class="className">
    <div class="HolyGrail-body">
      <main class="HolyGrail-content nes-container with-title">
        <slot></slot>
      </main>
      
      <slot name="left"></slot>
      <slot name="right"></slot>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  props: ['className'],
  components: {
  },
})
export default class HolyGrail extends Vue {}
</script>

<style>
/* https://philipwalton.github.io/solved-by-flexbox/demos/holy-grail/ */
.HolyGrail {
  display: flex;
  flex-direction: column;
}

.HolyGrail-body {
  display: flex;
  flex: 1;
}

.HolyGrail-content {
  flex: 1;
  overflow-x: hidden;
}

.HolyGrail-nav {
  /* put the nav on the left */
  order: -1;
}

.HolyGrail,
.HolyGrail-body {
  display: flex;
  flex-direction: column;
}

@media (min-width: 768px) {
  .HolyGrail-body {
    flex-direction: row;
    flex: 1;
  }
}
</style>
