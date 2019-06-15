<template>
  <div
    class="PlayerList"
  >
    <CharacterList
      title="Masters"
      :characters="masters"
    />

    <CharacterList
      title="Players"
      :characters="players"
    />
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import CharacterList from '@/components/CharacterList.vue';

@Component({
  components: {CharacterList},
})
export default class PlayerList extends Vue {

  private masters = [{
    id: 1,
    name: 'JoJi Joestar',
    level: 20,
    hp: 100,
    maxHp: 100,
    mp: 50,
    maxMp: 50,
  }];

  private players = [
    {
      id: 2,
      name: 'Luan Vitola',
      level: 10,
      hp: 100,
      maxHp: 100,
      mp: 50,
      maxMp: 50,
    },
    {
      id: 3,
      name: 'Ultimate Mercer',
      level: 10,
      hp: 75,
      maxHp: 100,
      mp: 50,
      maxMp: 50,
    },
    {
      id: 4,
      name: 'Jo Jorno',
      level: 10,
      hp: 5,
      maxHp: 100,
      mp: 10,
      maxMp: 50,
    },
    {
      id: 5,
      name: 'Verga Rina',
      level: 10,
      hp: 25,
      maxHp: 100,
      mp: 25,
      maxMp: 50,
    },

    ...Array.from({ length: 20 }, (_, i) => (
    {
      id: 6 + i,
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
