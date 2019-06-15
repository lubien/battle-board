<template>
  <div
    class="CharacterListItem"
  >
    <div class="CharacterListItem-avatar">
      <Avatar :name="name" :size="48" />
    </div>

    <div class="CharacterListItem-right">
      <span class="CharacterListItem-name">{{ name }}</span>
      <span v-if="level" class="CharacterListItem-level">Level {{ level }}</span>
      <div class="CharacterListItem-progress-container">
        <ProgressBar type="hp" :value="hp" :max="maxHp" />
        <ProgressBar type="mp" :value="mp" :max="maxMp" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';
import Avatar from '@/components/Avatar.vue';
import ProgressBar from '@/components/ProgressBar.vue';

@Component({
  components: {Avatar, ProgressBar},
})
export default class CharacterListItem extends Vue {
  @Prop({ default: '' }) public name!: string;
  @Prop({ required: false }) public level!: number | null;
  @Prop({ default: 100 }) public hp!: number;
  @Prop({ default: 100 }) public maxHp!: number;
  @Prop({ default: 50 }) public mp!: number;
  @Prop({ default: 50 }) public maxMp!: number;
}
</script>


<style>
.CharacterListItem {
  display: flex;
  margin: 15px;
  color: #fff;
}

.CharacterListItem > * {
  flex: 1;
}

.CharacterListItem-avatar {
  max-width: 48px;
}

.CharacterListItem-right {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.CharacterListItem-name,
.CharacterListItem-level,
.CharacterListItem-progress-container {
  display: block;
  text-align: left;
  margin-left: 10px;
}

.CharacterListItem-name {
  font-size: 15px;
}

.CharacterListItem-level {
  font-size: 12px;
  color: #cccccc;
}

.CharacterListItem-progress-container {
  margin-top: 5px;
}
</style>
