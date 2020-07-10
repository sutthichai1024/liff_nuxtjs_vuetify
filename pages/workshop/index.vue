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
          <Card
            :active="selectedWorkshop === 1"
            @moreDetail="moreDetail"
            @chooseWorkshop="chooseWorkshop(1)" />
          <Card
            :active="selectedWorkshop === 2"
            @moreDetail="moreDetail"
            @chooseWorkshop="chooseWorkshop(2)" />
          <Card
            :active="selectedWorkshop === 3"
            @moreDetail="moreDetail"
            @chooseWorkshop="chooseWorkshop(3)"
        /></v-col>
        <v-col>
          <div class="set-padding">
            <v-btn rounded color="primary w-100 mt-3 my-btn" dark @click="next"
              >Next</v-btn
            >
          </div>
        </v-col>
      </v-row>
      <v-dialog v-model="dialog" max-width="290">
        <v-card class="dialog-card">
          <v-img
            class="white--text align-end"
            height="200px"
            src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          >
          </v-img>
          <v-card-title class="headline">Design Thinking 1</v-card-title>

          <v-card-text>
            <p>Time : 13.00 - 16.30</p>
            <p>place : Room 102</p>
            <p class="detail">
              Design Thinking is a design methodology that provides a
              solution-base approach to solving problem. We will focus on the
              five-stage Design Thinking model, Empathize ,define(the problem),
              Ideate , Prototype and test
            </p>
            <p>
              Speaker <br />
              - Miss Yao <br />
              - Miss Tam
            </p>
          </v-card-text>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn class="text-primary" text @click="dialog = false">
              Ok
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-container>
  </div>
</template>

<script>
import Card from '~/components/Card'
export default {
  components: {
    Card,
  },
  data() {
    return {
      dialog: false,
      selectedWorkshop: 0,
    }
  },
  methods: {
    next() {},
    moreDetail() {
      this.dialog = true
    },
    chooseWorkshop(id) {
      this.selectedWorkshop = id
    },
  },
}
</script>

<style lang="scss" scoped>
.dialog-card {
  p {
    margin-bottom: 0;
  }
  .v-card__title.headline {
    font-size: 20px !important;
  }
  .v-card__text {
    padding-bottom: 0;
  }
  .detail {
    margin: 10px 0;
  }
}
</style>
