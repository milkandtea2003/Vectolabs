<template>
  <div class="CardGroup">
    <div class="Card">
      <div class="detail">
        <div class="blueIcon">
          <img src="../assets/check.svg" alt="check" />
        </div>
        <div class="info">
          <p>{{ tagCount }}</p>
          <span>Tags Assigned & Activated</span>
        </div>
      </div>
    </div>
    <div class="Card">
      <div class="detail">
        <div class="blueIcon">
          <img src="../assets/flag.svg" alt="check" />
        </div>
        <div class="info">
          <p>{{ ParticipantsStartLineCount }}</p>
          <span>Participants at the Starting Line</span>
        </div>
      </div>
    </div>
    <div class="Card">
      <div class="detail">
        <div class="blueIcon">
          <img src="../assets/question.svg" alt="check" />
        </div>
        <div class="info">
          <p>{{ AbsentCount }}</p>
          <span>Absent Participants</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AppCardGroup",
  data() {
    return {
      tagCount: 150,
      ParticipantsStartLineCount: 143,
      AbsentCount: 7
    }
  }
});
</script>

<style scoped>
.detail {
  display: flex;
  align-items: center;
}
.blueIcon {
  min-height: 60px;
  min-width: 60px;
  max-height: 60px;
  max-width: 60px;
  border-radius: 50%;
  background: #67b3ff;
  display: flex;
  justify-content: center;
  align-content: center;
  flex-wrap: wrap;
}

.blueIcon img {
  width: 80%;
  height: 100%;
  max-height: 48px;
}

.Card p {
  font-weight: 700;
  font-size: 25px;
  margin: 0;
}

.Card span {
  font-weight: 600;
  color: #7e7e7e;
  font-size: 1.1rem;
}

.info {
  margin-left: 30px;
  max-width: 60%;
}
</style>
