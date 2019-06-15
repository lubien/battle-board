<template>
  <div class="HolyGrail" :class="className">
    <div class="HolyGrail-body">
      <slot name="left"></slot>

      <main class="HolyGrail-content">
        <slot></slot>
      </main>
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
  overflow: hidden;
  height: 100vh;
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
