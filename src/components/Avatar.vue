<template>
  <div
    class="Avatar"
    :style="`
      background-color: ${backgroundColor};
      width: ${size}px;
      height: ${size}px;
    `"
    :class="{ 'Avatar-small': small }"
  >
    {{ initials }}
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';

@Component({
})
export default class Avatar extends Vue {
  @Prop({ default: '' }) public name!: string;
  @Prop({ default: 64 }) public size!: number;

  private backgroundColor: string = '#' + (Math.random().toString(16) + '000000').substring(2, 8);

  get initials() {
    if (this.name === '') {
      return '?';
    }

    const names = this.name.split(' ');

    if (names.length >= 2) {
      return names[0][0].toUpperCase() + names[1][0].toUpperCase();
    }

    return this.name.substring(0, 2).toUpperCase();
  }

  get small() {
    return this.size < 48;
  }
}
</script>


<style>
.Avatar {
  margin: 0 auto;
  border-radius: 50%;
  font-size: 1.5em;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
}

.Avatar-small {
  font-size: 1em;
}
</style>
