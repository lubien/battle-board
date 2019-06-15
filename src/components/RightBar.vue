<template>
  <SideBar class="RightBar">
    <SideBarInner>
      <NpcList />
    </SideBarInner>
  </SideBar>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import SideBar from '@/components/SideBar.vue';
import SideBarInner from '@/components/SideBarInner.vue';
import NpcList from '@/components/NpcList.vue';

@Component({
  components: {
    SideBar,
    SideBarInner,
    NpcList,
  },
})
export default class RightBar extends Vue {
}
</script>

<style scoped>
.RightBar.SideBar {
  width: 220px;
}
</style>
