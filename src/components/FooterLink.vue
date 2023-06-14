<template>
  <q-item clickable tag="a" target="_blank" :href="link" class="footlink">
    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "FooterLink",
  props: {
    title: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      default: "#",
    },
  },
});
</script>
