<template>
  <div style="display: flex">
    <div class="SidebarArea">
      <AppSidebar :isOpen="isSidebarOpen" @toggle="toggleSidebar" />
      <img
        src="./assets/hamburger.png"
        alt="Open Sidebar"
        @click="toggleSidebar"
        class="hamburger"
      />
    </div>

    <div class="container">
      <AppHeader @toggleSidebar="toggleSidebar" />

      <div class="content">
        <AppParticipantsList />

        <div class="RightContainer">
          <OpenStreetMap />

          <AppCardGroup />
        </div>
        
      </div>
    </div>
  </div>
  <AppFooter />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import AppSidebar from "./components/AppSidebar.vue";
import AppHeader from "./components/AppHeader.vue";
import AppParticipantsList from "./components/AppParticipantsList.vue";
import OpenStreetMap from "./components/OpenStreetMap.vue";
import AppCardGroup from "./components/AppCardGroup.vue";
import AppFooter from "./components/AppFooter.vue";

export default defineComponent({
  name: "App",
  components: {
    AppSidebar,
    AppHeader,
    AppParticipantsList,
    OpenStreetMap,
    AppCardGroup,
    AppFooter
},
  data() {
    return {
      isSidebarOpen: false,
    };
  },
  methods: {
    toggleSidebar() {
      this.isSidebarOpen = !this.isSidebarOpen;
    },
  },
});
</script>
