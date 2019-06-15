<template>
  <div
    class="CharacterList"
  >
    <h5 class="CharacterList-view-header">{{ title }}</h5>

    <CharacterListItem
      v-for="character in characters"
      :key="character.id"
      :name="character.name"
      :level="character.level"
      :hp="character.hp"
      :maxHp="character.maxHp"
      :mp="character.mp"
      :maxMp="character.maxMp"
    />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import CharacterListItem from '@/components/CharacterListItem.vue';

@Component({
  components: {
    CharacterListItem,
  },
})
export default class CharacterList extends Vue {
  @Prop({ required: true }) public title!: string;
  @Prop({ default: [] }) public characters!: Array<{
    id: number,
    name: string,
    level: number,
    hp: number,
    maxHp: number,
    mp: number,
    maxMp: number,
  }>;
}
</script>


<style>
.CharacterList-view-header {
  color: #fff;
}
</style>
