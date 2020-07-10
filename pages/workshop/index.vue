<template>
  <div>
    <v-app-bar color="primary" dense flat dark>
      <v-toolbar-title>Register Workshop</v-toolbar-title>
    </v-app-bar>
    <v-container class="pt-0 pb-0">
      <v-row>
        <v-col cols="12">
          <div class="mt-3 text-primary text-title text-center">
            10 July 2020
          </div>
        </v-col>
        <v-col cols="12">
          <v-card class="mx-auto" max-width="400">
            <v-img
              class="white--text align-end"
              height="200px"
              src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
            >
              <div class="more-detail">More Detail</div>
            </v-img>
            <div class="card-content">
              <div>
                <v-card-text class="text--primary">
                  <h1>Design Thinking 1</h1>
                </v-card-text>
                <v-card-subtitle class="pt-0">DMC Team Dev</v-card-subtitle>
              </div>
              <v-btn class="circle"><v-icon>check</v-icon></v-btn>
            </div>
          </v-card>
        </v-col>
        <v-col cols="12">
          <v-card class="mx-auto active" max-width="400">
            <v-img
              class="white--text align-end"
              height="200px"
              src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
            >
              <div class="more-detail">More Detail</div>
            </v-img>
            <div class="card-content">
              <div>
                <v-card-text class="text--primary">
                  <h1>Design Thinking 2</h1>
                </v-card-text>
                <v-card-subtitle class="pt-0">DMC Team Dev</v-card-subtitle>
              </div>
              <v-btn class="circle"><v-icon>check</v-icon></v-btn>
            </div>
          </v-card>
        </v-col>
        <v-col cols="12">
          <v-card class="mx-auto" max-width="400">
            <v-img
              class="white--text align-end"
              height="200px"
              src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
            >
              <div class="more-detail">More Detail</div>
            </v-img>
            <div class="card-content">
              <div>
                <v-card-text class="text--primary">
                  <h1>Design Thinking 3</h1>
                </v-card-text>
                <v-card-subtitle class="pt-0">DMC Team Dev</v-card-subtitle>
              </div>
              <v-btn class="circle"><v-icon>check</v-icon></v-btn>
            </div>
          </v-card>
        </v-col>
        <v-col>
          <div class="set-padding">
            <v-btn rounded color="primary w-100 mt-3 my-btn" dark @click="next"
              >Next</v-btn
            >
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  methods: {
    next() {},
  },
}
</script>

<style lang="scss" scoped>
.more-detail {
  font-size: 12px;
  color: #1a56be;
  border-radius: 25px;
  padding: 10px 20px;
  background: #fff;
  font-weight: bold;
  display: inline;
  position: absolute;
  bottom: 11px;
  right: 11px;
}
.v-card__text {
  padding: 0;
  padding-bottom: 5px;
  h1 {
    font-size: 24px;
  }
}
.circle {
  border-radius: 50%;
  height: 32px !important;
  width: 32px !important;
  min-width: auto !important;
  color: #fff;
  background: rgba($color: #1a56be, $alpha: 0.3) !important;
  align-self: center;
}
.card-content {
  display: flex;
  justify-content: space-between;
  padding: 15px;
}
.v-card__subtitle {
  padding: 0;
}
.v-card + .v-card {
  margin-top: 30px;
}
.v-card.active {
  .circle {
    background: rgba($color: #1a56be, $alpha: 1) !important;
  }
  .v-image {
    &::before {
      content: 'Selected';
      font-weight: bold;
      height: 100%;
      width: 100%;
      font-size: 24px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: rgba($color: #1a56be, $alpha: 1) !important;
    }
  }
}
</style>
