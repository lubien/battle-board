<template>
  <div
    class="SideBarInner"
    v-bar
  >
    <div><slot></slot></div>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';

@Component({
})
export default class SideBarInner extends Vue {
}
</script>


<style>
.SideBarInner {
  background-color: #363E47;
  overflow-y: auto;
}

@media (min-width: 768px) {
  .SideBarInner {
    width: 220px;
  }
}

.SideBarInner .vb-dragger {
  background-color: rgba(255, 255, 255, .2);
  right: 3px;
}

.SideBarInner .vb-dragger .vb-dragger-styler {
  margin: 5px 5px 5px 0;
  border-radius: 20px;
}
</style>
