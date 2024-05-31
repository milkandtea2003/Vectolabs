<template>
  <div>
    <span style="color: #8e8e8e">Data last update {{ lastUpdate }}</span>

    <div class="participantsArea">
      <div class="participantHeader">
        <h2 class="title">Participants List</h2>
        <div class="searchGroup">
          <input type="text" placeholder="Search..." class="searchInput" />
          <button class="searchButton">
            <img src="../assets/search.svg" alt="search" />
          </button>
        </div>
      </div>
      <div class="participantsList">
        <div
          v-for="(participant, index) in participants"
          :key="index"
          class="participantsCard"
        >
          <div class="leftContent">
            <p class="participantName">{{ participant.name }}</p>
            <div>
              <table style="border-collapse: separate; border-spacing: 0">
                <tr v-for="(value, key) in participant.details" :key="key">
                  <td class="greyText">{{ key }}</td>
                  <td
                    :class="{
                      redText: shouldHighlightRed(key, value),
                      boldText: shouldBold(key, value),
                    }"
                    class="statusText"
                  >
                    : {{ value
                    }}<span
                      style="color: #b4b4b3"
                      v-if="key === 'Battery Level' && parseInt(value) < 20"
                    >
                      (Charge Now)</span
                    >
                  </td>
                </tr>
              </table>
            </div>
          </div>
          <div class="rightChevron">
            <button class="chevronRight">
              <img src="../assets/chevronRight.svg" alt="chevron" />
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AppParticipantsList",
  data() {
    return {
      lastUpdate: "10 minutes ago",
      participants: [
        {
          name: "Faizal Ali",
          details: {
            "Battery Level": "77%",
            "Device Status": "Connected",
            Location: "Within zone",
            "Panic Button": "Standby",
          },
        },
        {
          name: "Ikhwan Ayub",
          details: {
            "Battery Level": "15%",
            "Device Status": "Connected",
            Location: "Within zone",
            "Panic Button": "Standby",
          },
        },
        {
          name: "Yahya Abd Rahman",
          details: {
            "Battery Level": "77%",
            "Device Status": "Disconnected",
            Location: "Leaving Zone",
            "Panic Button": "ACTIVATED!",
          },
        },
        {
          name: "Haziq Haikal",
          details: {
            "Battery Level": "77%",
            "Device Status": "Connected",
            Location: "Within zone",
            "Panic Button": "Standby",
          },
        },
        {
          name: "Faizal Ali",
          details: {
            "Battery Level": "77%",
            "Device Status": "Connected",
            Location: "Within zone",
            "Panic Button": "Standby",
          },
        },
        {
          name: "Faizal Ali",
          details: {
            "Battery Level": "77%",
            "Device Status": "Connected",
            Location: "Within zone",
            "Panic Button": "Standby",
          },
        },
      ],
    };
  },
  methods: {
    shouldHighlightRed(key: string, value: string): boolean {
      return (
        (key === "Device Status" && value === "Disconnected") ||
        (key === "Location" && value === "Leaving Zone") ||
        (key === "Panic Button" && value === "ACTIVATED!") ||
        (key === "Battery Level" && value < "20%")
      );
    },
    shouldBold(key: string, value: string) {
      return key === "Panic Button" && value === "ACTIVATED!";
    },
  },
});
</script>

<style scoped>
.title {
  font-size: 18px;
  font-weight: bold;
}
table .greyText {
  padding-right: 35px;
}
@media screen and (max-width: 576px) {
  table .greyText {
    padding-right: 30px;
    font-size: 14px;
  }
  table td {
    font-size: 14px;
  }
}

@media screen and (max-width: 500px) {
  table .greyText {
    padding-right: 20px;
    font-size: 13px;
  }
  table td {
    font-size: 13px;
  }
}

@media screen and (max-width: 430px) {
  table .greyText {
    padding-right: 0;
    font-size: 10px;
  }
  table td {
    font-size: 10px;
  }
}
</style>
