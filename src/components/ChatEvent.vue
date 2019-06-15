<template>
  <div class="ChatEvent">
    <template v-if="event.type === 'text'">
      <div
        class="ChatEvent-message"
        :class="{ 'ChatEvent-message-self': event.name === 'Joseph Joestar' }"
      >
        <Avatar :size="48" :name="event.name" />
        <div class="ChatEvent-message-body">{{ event.text }}</div>
      </div>
    </template>

    <template v-else>
      <div class="ChatEvent-action">
        <div class="ChatEvent-action-strike">&nbsp;</div>
        
        <div v-if="event.action === 'attack'" class="ChatEvent-action-center">
          <Avatar :size="36" :name="event.name" />
          <span>
            <img src="../assets/2-swords.svg" alt="attacks" class="ChatEvent-action-image">
          </span>
          <Avatar :size="36" :name="event.against" />
        </div>

        <div v-else-if="event.action === 'guard'" class="ChatEvent-action-center">
          <span>
            <img src="../assets/shield.svg" alt="guard" class="ChatEvent-action-image">
          </span>
          <Avatar :size="36" :name="event.name" />
          <span>
            <img src="../assets/shield.svg" alt="guard" class="ChatEvent-action-image">
          </span>
        </div>

        <div class="ChatEvent-action-strike">&nbsp;</div>
      </div>
    </template>
  </div>
</template>



<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import Avatar from '@/components/Avatar.vue';

@Component({
  components: {Avatar},
})
export default class ChatEvent extends Vue {
  @Prop({ required: true }) public event!: {
    id: number,
    type: 'text' | 'action',
    name: string,
    text?: string,
    action?: 'attack' | 'guard',
    against?: string,
  };
}
</script>

<style>
.ChatEvent {

}

.ChatEvent-message {
  text-align: left;
  display: flex;
  align-items: center;
}

.ChatEvent-message-self {
  text-align: right;
  justify-content: flex-end;
}

.ChatEvent-message-self .Avatar {
  order: 1;
}

.ChatEvent-message .Avatar {
  margin: 15px 5px;
}

.ChatEvent-message-body {
  background-color: #A5B6C2;
  border-radius: 5px;
  height: 36px;
  color: #fff;
  display: flex;
  align-items: center;
  padding: 5px 15px;
  max-width: 100%;
  min-width: 300px;
}

.ChatEvent-action {
  display: flex;
}

.ChatEvent-action-strike {
  flex: 1;
  height: 20px;
  border-bottom: 1px solid #b3b3b3;
  text-align: center;
}

.ChatEvent-action-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.ChatEvent-action .Avatar {
  margin: 0 10px;
}

.ChatEvent-action-image {
  width: 32px;
  height: auto;
}
</style>
