<template>
  <div class="SideBar">
    <slot></slot>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  },
})
export default class SideBar extends Vue {
}
</script>

<style>
.SideBar {
  display: flex;
}

.SideBar,
.SideBar > * {
  height: 100%;
}
</style>
