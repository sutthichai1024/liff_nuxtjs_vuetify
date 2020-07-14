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
              <h1 class="text-title mt-4">Thankyou</h1>
              <p class="mt-7">
                Thanks for completing this survey,<br />
                your feedback will help us improve the next event.
              </p>
            </div>

            <div
              class="w-100 text-center my-btn text-primary outlined mt-100"
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
  methods: {
    close() {},
  },
}
</script>

<style></style>
