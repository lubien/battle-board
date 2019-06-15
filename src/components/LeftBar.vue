<template>
  <SideBar class="LeftBar">
    <div class="LeftBar-action-bar">
      <div class="LeftBar-avatar">
        <Avatar
          name="Joseph Joestar"
        />
      </div>

      <button
        v-for="item in sidebarItems"
        :key="item.key"
        class="LeftBar-left-btn"
        :class="{ 'LeftBar-left-btn-active': openedSidebarItem === item.key }"
        @click="openSidebarItem(item.key)"
      >
        <fa :icon="item.icon" />
      </button>
    </div>

    <SideBarInner>
      <PlayerList />
    </SideBarInner>
  </SideBar>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import SideBar from '@/components/SideBar.vue';
import SideBarInner from '@/components/SideBarInner.vue';
import Avatar from '@/components/Avatar.vue';
import PlayerList from '@/components/PlayerList.vue';

@Component({
  components: {
    SideBar,
    SideBarInner,
    Avatar,
    PlayerList,
  },
})
export default class LeftBar extends Vue {
  private openedSidebarItem = 'players';

  private sidebarItems = [
    { icon: 'list', key: 'players' },
    { icon: 'list', key: 'attack' },
    { icon: 'list', key: 'guard' },
  ];

  private openSidebarItem(key: string) {
    this.openedSidebarItem = key;
  }
}
</script>


<style scoped>
.LeftBar.SideBar {
  width: 320px;
}
</style>

<style>
.LeftBar-action-bar {
  background-color: #303841;
  width: 100px;
  padding-top: 32px;
}

.LeftBar-avatar {
  width: 100%;
  text-align: center;
  margin-bottom: 64px;
}

.LeftBar-left-btn {
  background-color: unset;
  color: #A5B5C0;
  font-size: 24px;
  width: 100%;
  height: 64px;
  cursor: pointer;
  outline: none;
  border: unset;
  border-left: solid 2px rgba(0, 0, 0, 0);
}

.LeftBar-left-btn-active {
  background-color: #363E47;
  border-left-color:#54D48C;
}
</style>
