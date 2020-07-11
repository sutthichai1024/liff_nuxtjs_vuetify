<template>
  <div>
    <v-app-bar color="primary" dense flat dark>
      <v-toolbar-title>AGENDA</v-toolbar-title>
    </v-app-bar>
    <v-sheet elevation="6">
      <v-tabs v-model="tab" grow>
        <v-tab v-for="item in items" :key="item.tab">
          {{ item.tab }}
        </v-tab>
      </v-tabs>
    </v-sheet>
    <v-tabs-items v-model="tab">
      <v-tab-item v-for="item in items" :key="item.tab">
        <v-container class="pt-0">
          <v-row>
            <v-col cols="12">
              <v-card class="agenda-card">
                <v-card-text>
                  <p class="time mb-0">10:00 - 11:45</p>
                  <v-row>
                    <v-col cols="4" class="text-center pt-2 pb-0">
                      <img
                        src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                        class="agenda-image"
                      />
                    </v-col>
                    <v-col cols="8" class="pt-2 pb-0">
                      <v-card-title
                        class="pl-0 pt-0 pb-3 text-primary text-title"
                        >INTRODUCTIONS</v-card-title
                      ><v-card-subtitle class="pl-0 pt-0 pb-0"
                        >DMC Team</v-card-subtitle
                      >
                    </v-col>
                  </v-row>
                </v-card-text>
              </v-card>
              <v-card class="agenda-card card-set">
                <v-card-text>
                  <p class="time mb-0">10:00 - 11:45</p>
                  <v-row>
                    <v-col cols="4" class="text-center pt-2 pb-0">
                      <img
                        src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                        class="agenda-image"
                      />
                    </v-col>
                    <v-col cols="8" class="pt-2 pb-0">
                      <v-card-title
                        class="pl-0 pt-0 pb-3 text-primary text-title"
                        >INTRODUCTIONS</v-card-title
                      ><v-card-subtitle class="pl-0 pt-0 pb-0"
                        >DMC Team</v-card-subtitle
                      >
                    </v-col>
                  </v-row>
                </v-card-text>
                <hr />
                <v-card-text>
                  <v-row>
                    <v-col cols="4" class="text-center pt-2 pb-0">
                      <img
                        src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                        class="agenda-image"
                      />
                    </v-col>
                    <v-col cols="8" class="pt-2 pb-0">
                      <v-card-title
                        class="pl-0 pt-0 pb-3 text-primary text-title"
                        >INTRODUCTIONS</v-card-title
                      ><v-card-subtitle class="pl-0 pt-0 pb-0"
                        >DMC Team</v-card-subtitle
                      >
                    </v-col>
                  </v-row>
                </v-card-text>
                <hr />
                <v-card-text>
                  <v-row>
                    <v-col cols="4" class="text-center pt-2 pb-0">
                      <img
                        src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
                        class="agenda-image"
                      />
                    </v-col>
                    <v-col cols="8" class="pt-2 pb-0">
                      <v-card-title
                        class="pl-0 pt-0 pb-3 text-primary text-title"
                        >INTRODUCTIONS</v-card-title
                      ><v-card-subtitle class="pl-0 pt-0 pb-0"
                        >DMC Team</v-card-subtitle
                      >
                    </v-col>
                  </v-row>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-tab-item>
    </v-tabs-items>
  </div>
</template>
<script>
export default {
  data() {
    return {
      tab: null,
      items: [
        { tab: '20 July 20', content: 'Tab 1 Content' },
        { tab: '21 July 20', content: 'Tab 2 Content' },
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
.v-tabs {
  margin-bottom: 15px;
}
.v-tab {
  color: #4d4d4d;
  font-weight: bold;
  background: #efefef;
  &.v-tab--active {
    color: #1a56be !important;
  }
  & + .v-tab {
    border-left: #bdbdbd solid 1px;
  }
}
.agenda-card {
  .time {
    color: #1a56be;
    font-weight: bold;
  }
  .agenda-image {
    width: 50px;
    height: 50px;
    object-fit: cover;
    border-radius: 50%;
  }
  & + .agenda-card {
    margin-top: 15px;
  }
  &.card-set {
    border-left: 3px solid #1a56be;
  }
  hr {
    width: 80%;
    margin: 0 auto;
    height: 1px;
    background: #bdbdbd;
    border: 0;
  }
}
</style>
