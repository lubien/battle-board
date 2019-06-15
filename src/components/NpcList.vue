<template>
  <div
    class="NpcList"
  >
    <CharacterList
      title="NPCs"
      :characters="npcs"
    />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import CharacterList from '@/components/CharacterList.vue';

@Component({
  components: {CharacterList},
})
export default class NpcList extends Vue {
  private npcs = [
    ...Array.from({ length: 20 }, (_, i) => (
    {
      id: i + 1,
      name: `Bot ${i + 1}`,
      level: 10,
      hp: 100,
      maxHp: 100,
      mp: 50,
      maxMp: 50,
    })),
  ];
}
</script>
