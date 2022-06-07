<template>
  <v-row dense>
    <v-col cols="4">
      <v-select
        label="Country"
        outlined
        v-model="selectedCountry"
        :items="countryCode"
        hide-details="false"
      >
        <template v-slot:selection="{ item }">
          <img style="max-width: 1.6rem" :src="item.flag" />
        </template>
        <template v-slot:item="{ item }">
          {{ item.name }}
        </template>
      </v-select>
    </v-col>

    <v-col cols="8">
      <v-text-field
        :prefix="selectedCountry.number"
        placeholder="123456789"
        outlined
        hide-details="false"
        v-model="phoneNumber"
      ></v-text-field>
    </v-col>

    <v-col cols="12">
      <v-btn @click="sendMessage" color="primary" block> Send message </v-btn>
    </v-col>
  </v-row>
</template>

<script>
import data from "../data/countryCode.json";
export default {
  data() {
    return {
      selectedCountry: {
        name: "Malaysia",
        flag: "https://upload.wikimedia.org/wikipedia/commons/6/66/Flag_of_Malaysia.svg",
        number: "+60",
      },
      phoneNumber: "",
      countryCode: [],
    };
  },
  fetch() {
    this.countryCode = data;
  },
  methods: {
    sendMessage() {
      if (this.phoneNumber !== "") {
        let finalRoute = `https://wa.me/${this.selectedCountry.number}${this.phoneNumber}`;
        window.open(finalRoute, "_blank");
      } else {
        alert("Please insert phone number");
      }
    },
  },
};
</script>
