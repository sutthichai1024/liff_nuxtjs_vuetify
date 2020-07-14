<template>
  <div>
    <v-app-bar color="primary" dense flat dark>
      <v-toolbar-title>Register</v-toolbar-title>
    </v-app-bar>
    <v-container class="pt-0 pb-0">
      <v-row>
        <v-col cols="12">
          <div class="set-pading">
            <div class="text-center mt-10">
              <img src="~/assets/success_register.png" alt="" width="236px" />
              <h1 class="text-title">Welcome, {{ name }}</h1>
              <p class="mt-7">
                Welcome to the event,<br />
                Tons of workshop are waiting for you.<br />
                we hope you have a good time here
              </p>
            </div>
            <v-btn
              rounded
              color="primary w-100 mt-10 my-btn"
              dark
              @click="workshop"
              >Register Workshop</v-btn
            >
            <div
              class="w-100 text-center my-btn text-primary outlined mt-5"
              @click="close"
            >
              Close
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: this.$store.getters.getRegister.firstName,
    }
  },
  methods: {
    workshop() {
      this.$router.push('workshop')
    },
    close() {
      const liff = window.liff
      liff.closeWindow()
    },
  },
}
</script>

<style></style>
