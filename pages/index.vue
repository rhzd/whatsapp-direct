<template>
  <v-container>
    <v-row justify="center" align="center">
      <v-col class="top-div" cols="12">
        <HeaderWriting />
      </v-col>
      <v-col cols="12">
        <HeaderLottie />
      </v-col>
      <v-col class="bottom-div" cols="12">
        <PhoneNumberForm />
      </v-col>
    </v-row>
  </v-container>
</template>

<style>
.top-div {
  margin-top: 0.2rem;
}
.bottom-div {
  position: absolute;
  bottom: 0.2rem;
}
</style>
