<template>
  <div class="header">
    <h1 class="title">Dashboard</h1>

    <div class="RightArea">
      <button class="ring">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 448 512"
          class="icon"
        >
          <path
            d="M224 0c-17.7 0-32 14.3-32 32V51.2C119 66 64 130.6 64 208v18.8c0 47-17.3 92.4-48.5 127.6l-7.4 8.3c-8.4 9.4-10.4 22.9-5.3 34.4S19.4 416 32 416H416c12.6 0 24-7.4 29.2-18.9s3.1-25-5.3-34.4l-7.4-8.3C401.3 319.2 384 273.9 384 226.8V208c0-77.4-55-142-128-156.8V32c0-17.7-14.3-32-32-32zm45.3 493.3c12-12 18.7-28.3 18.7-45.3H224 160c0 17 6.7 33.3 18.7 45.3s28.3 18.7 45.3 18.7s33.3-6.7 45.3-18.7z"
          />
        </svg>
      </button>
      <div>
        <button class="dropdown" @click="toggleDropdown">
          <img src="../assets/Kuromi.png" alt="asd" class="avatar" />
          <span>{{ userName }}</span>
          <img src="../assets/dropdown.svg" alt="dropdown" class="caret" />
        </button>
        <div :class="{ 'dropdown-menu': true, 'show': isDropdownOpen }">
          <ul>
            <li>Menu Item 1</li>
            <li>Menu Item 2</li>
            <li>Menu Item 3</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AppHeader",
  data() {
    return {
      userName: "Per.Putrajaya",
      isDropdownOpen: false,
    };
  },
  methods: {
    toggleSidebar() {
      this.$emit("toggleSidebar");
    },
    toggleDropdown() {
      this.isDropdownOpen = !this.isDropdownOpen;
    },
  },
});
</script>

<style scoped>
.title {
  font-size: clamp(1.25rem, 5vw, 1.5rem);
  font-weight: 500;
  color: #99cafd;
}

@media screen and (max-width: 440px) {
  .dropdown span {
    display: none;
  }
}

.dropdown {
  background: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: max-content;
  border-radius: 50px;
  border: none;
  box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
  height: 36px;
  color: #67b3ff;
  padding: 0px 5px 0px 0px;
  gap: 0.625rem;
  position: relative;
  transition: all 0.5s ease-in-out;
  cursor: pointer;

}
.dropdown-menu {
  position: absolute;
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  border: none;
  z-index: 100001;
  margin-right: auto;
  opacity: 0;
  visibility: hidden;
  transition: opacity 0.3s ease, visibility 0.3s ease;
}

.dropdown-menu ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.dropdown-menu li {
  padding: 8px 16px;
  cursor: pointer;
}

.dropdown-menu li:hover {
  background: #f5f5f5;
}

.dropdown-menu.show {
  opacity: 1;
  visibility: visible;
}
</style>
