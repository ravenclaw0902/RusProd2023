<template>
  <div class="q-mx-none q-my-none q-px-none q-py-none bottom-body">
    <div class="row items-center fab-group">
      <q-fab color="primary" icon="keyboard_arrow_left" direction="left">
        <q-fab-action color="primary" glossy @click="onClickMail" icon="mail" />
        <q-fab-action
          color="primary"
          glossy
          @click="onClickPhone"
          icon="phone"
        />
        <q-fab-action
          color="primary"
          glossy
          @click="onClickMappoint"
          icon="room"
        />
        <q-fab-action
          color="primary"
          glossy
          @click="onClickScheme"
          icon="airplay"
        />
      </q-fab>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "FloatActionButtons",
  setup() {
    return {
      onClickMail() {
        console.log("Clicked on a fab action mail");
      },
      onClickPhone() {
        console.log("Clicked on a fab action phone");
      },
      onClickMappoint() {
        console.log("Clicked on a fab action map");
      },
      onClickScheme() {
        console.log("Clicked on a fab action scheme");
      },
    };
  },
});
</script>
