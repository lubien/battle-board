<template>
  <HolyGrail class="Room">
    <template slot="header">
      Batalha
    </template>

    <template>
      <TurnQueue />
    </template>

    <template slot="left">
      <LeftBar />
    </template>

    <template slot="right">
      <RightBar />
    </template>
  </HolyGrail>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HolyGrail from '@/components/HolyGrail.vue';
import LeftBar from '@/components/LeftBar.vue';
import RightBar from '@/components/RightBar.vue';
import TurnQueue from '@/components/TurnQueue.vue';

@Component({
  components: {
    HolyGrail,
    LeftBar,
    RightBar,
    TurnQueue,
  },
})
export default class Room extends Vue {}
</script>

<style>
.Room {
  max-height: 100vh;
}

.Room .HolyGrail-nav {
  min-width: 320px;
  max-width: 360px;
}

.Room .HolyGrail-body {
  height: 100vh;
}
</style>
