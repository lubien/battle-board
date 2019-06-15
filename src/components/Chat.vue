<template>
  <div
    class="Chat"
  >    
    <div class="Chat-messages">
      <ChatEvent
        v-for="event in events"
        :key="event.id"
        :event="event"
      />
    </div>

    <div class="Chat-form">
      <input type="text" class="Chat-input">
      <button class="Chat-submit">Send</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import ChatEvent from '@/components/ChatEvent.vue';

@Component({
  components: {ChatEvent},
})
export default class Chat extends Vue {
  private events = [
    {
      id: 1,
      type: 'text',
      name: 'Joseph Joestar',
      text: 'Lorem ipsum dolor',
    },
    {
      id: 2,
      type: 'action',
      name: 'Joseph Joestar',
      action: 'attack',
      against: 'Luan Vitola',
    },
    {
      id: 3,
      type: 'text',
      name: 'Luan Vitols',
      text: 'Lorem ipsum',
    },
    {
      id: 4,
      type: 'action',
      name: 'Luan Vitols',
      action: 'guard',
    },
    {
      id: 5,
      type: 'text',
      name: 'Joseph Joestar',
      text: 'Lorem ipsum',
    },
    {
      id: 6,
      type: 'action',
      name: 'Rian Vergara',
      action: 'attack',
      against: 'Alex Mercer',
    },
    {
      id: 7,
      type: 'text',
      name: 'Filthy Frank',
      text: 'Lorem ipsum dolor',
    },
  ];
}
</script>

<style>
.Chat {
  width: 100%;
  border-top: 1px solid #dedede;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.Chat-messages {
  flex: 1;
  padding: 15px;
}

.Chat-form {
  height: 48px;
  width: 100%;
  display: flex;
  align-items: center;
  background-color: #A5B6C2;
}

.Chat-input {
  flex: 1;
  height: 100%;
  width: 100%;
  background-color: rgba(0, 0, 0, 0);
  border: 0;
  padding: 0 15px;
  color: #fff;
  font-size: 1.2em;
  outline: unset;
}

.Chat-submit {
  width: 64px;
  height: 36px;
  font-size: 1.2em;
  margin-right: 5px;
  background-color: #fff;
  border: 1px solid #dedede;
  border-radius: 5px;
}
</style>
