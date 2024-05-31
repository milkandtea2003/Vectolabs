<template>
  <div :class="{ 'sidebar': true, 'open': isOpen }">
    <div class="SideBarTitle">
      <h2>Sidebar</h2>
      <button @click="$emit('toggle')" class="closeSidebar">X</button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AppSidebar",
  props: {
    isOpen: {
      type: Boolean,
      required: true,
    },
  },
});
</script>
