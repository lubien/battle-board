<template>
  <progress 
    class="ProgresBar"
    :class="{
      [`ProgresBar-${type}`]: true,
      [`ProgresBar-${status}`]: true,
    }"
    :value="value"
    :max="max"
  ></progress>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';

@Component({
})
export default class ProgresBar extends Vue {
  @Prop({ default: 0 }) private value!: number;
  @Prop({ default: 100 }) private max!: number;
  @Prop({ default: 'hp' }) private type!: string;

  get status() {
    const x = this.value / this.max;

    if (x > 0.5) {
      return 'fine';
    }

    if (x > 0.2) {
      return 'warn';
    }

    return 'danger';
  }
}
</script>


<style>
.ProgresBar {
  appearance: none;
}

.ProgresBar {
  appearance: none;
  display: block; /* default: inline-block */
  width: 100%;
  margin: 1px 1px 2px;
  padding: 0;
  border: none;
  background: #303841;
  border-radius: 3px;
}

/* webkit */
@media screen and (-webkit-min-device-pixel-ratio:0) {
  .ProgresBar {
    height: 10px;
  }
}

.ProgresBar::-webkit-progress-bar {
  background: transparent;
}
  
.ProgresBar::-webkit-progress-value {  
  border-radius: 3px;
  background-color: #fff;
}

.ProgresBar-hp::-webkit-progress-value, 
.ProgresBar-hp::-moz-progress-bar {  
  background-color: #fe5400!important;
}

.ProgresBar-hp.ProgresBar-warn::-webkit-progress-value, 
.ProgresBar-hp.ProgresBar-warn::-moz-progress-bar {  
  background-color: #ff0000;
}

.ProgresBar-hp.ProgresBar-danger::-webkit-progress-value,
.ProgresBar-hp.ProgresBar-danger::-moz-progress-bar,
.ProgresBar-hp.ProgresBar-danger[aria-valuenow]:before {  
  background-color: #861617;
}

.ProgresBar-mp::-webkit-progress-value {  
  background: #497dc6;
}
</style>
