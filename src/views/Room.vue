<template>
  <HolyGrail class="Room">
    <template slot="header">
      Batalha
    </template>

    <template>
      <div class="Room-main">
        <TurnQueue />
        <Chat />
      </div>
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
import Chat from '@/components/Chat.vue';

@Component({
  components: {
    HolyGrail,
    LeftBar,
    RightBar,
    TurnQueue,
    Chat,
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

.Room-main {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
</style>
