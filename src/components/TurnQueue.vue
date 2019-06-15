<template>
  <div
    class="TurnQueue"
  >
    <div
      v-for="(character, i) in visibleCharacters"
      :key="i"
      class="TurnQueue-avatar-container"
      :class="{ 'TurnQueue-avatar-container-active': i === 0 }"
    >
      <Avatar
        :name="character.name"
        :size="i === 0 ? 64 : 48"
      />

      <span v-if="i === 0">Next</span>
    </div>
    
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import Avatar from '@/components/Avatar.vue';

@Component({
  components: {Avatar},
})
export default class TurnQueue extends Vue {
  private characters = [
    {
      name: 'Luan Vitola',
    },
    {
      name: 'Ultimate Mercer',
    },
    {
      name: 'Jo Jorno',
    },
    {
      name: 'Verga Rina',
    },

    ...Array.from({ length: 20 }, (_, i) => (
    {
      name: `Bot ${i + 1}`,
    })),
  ];

  get visibleCharacters() {
    if (this.characters.length < 10) {
      return this.characters;
    }

    const visible = this.characters.slice(0, 9);
    const countRest = this.characters.slice(9).length;

    const name = countRest > 9
      ? '9+'
      : `${countRest}`;

    return visible.concat({
      name,
    });
  }
}
</script>

<style>
.TurnQueue {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-bottom: 12px;
}

.TurnQueue-avatar-container {
  margin: 0px 3px;
}

.TurnQueue-avatar-container.TurnQueue-avatar-container-active {
  margin-top: 16px;
}

.TurnQueue-avatar-container span {
  font-size: .8em;
}
</style>
