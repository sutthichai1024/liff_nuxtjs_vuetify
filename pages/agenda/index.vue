<template>
  <div>
    <v-app-bar color="primary" dense flat dark>
      <v-toolbar-title>AGENDA</v-toolbar-title>
    </v-app-bar>
    <v-sheet elevation="6">
      <v-tabs v-model="tab" grow>
        <v-tab v-for="item in agenda" :key="item.date">
          {{ item.date }}
        </v-tab>
      </v-tabs>
    </v-sheet>
    <v-tabs-items v-model="tab">
      <v-tab-item v-for="item in agenda" :key="item.date">
        <v-container class="pt-0">
          <v-row>
            <v-col
              v-for="session in item.sessions"
              :key="session.title"
              cols="12"
            >
              <v-card
                class="agenda-card"
                :class="session.type === 'set' ? 'card-set' : ''"
              >
                <v-card-text v-if="session.type !== 'set'">
                  <p class="time mb-0">{{ session.time }}</p>
                  <v-row>
                    <v-col cols="4" class="text-center pt-2 pb-0">
                      <img :src="session.image" class="agenda-image" />
                    </v-col>
                    <v-col cols="8" class="pt-2 pb-0">
                      <v-card-title
                        class="pl-0 pt-0 pb-3 text-primary text-title"
                        >{{ session.title }}</v-card-title
                      ><v-card-subtitle class="pl-0 pt-0 pb-0">{{
                        session.spaker
                      }}</v-card-subtitle>
                    </v-col>
                  </v-row>
                </v-card-text>
                <div v-else>
                  <v-card-text
                    v-for="sessionSet in session.sessionSet"
                    :key="sessionSet.title"
                  >
                    <p class="time mb-0">{{ session.time }}</p>
                    <v-row>
                      <v-col cols="4" class="text-center pt-2 pb-0">
                        <img :src="sessionSet.image" class="agenda-image" />
                      </v-col>
                      <v-col cols="8" class="pt-2 pb-0">
                        <v-card-title
                          class="pl-0 pt-0 pb-3 text-primary text-title"
                          >{{ sessionSet.title }}</v-card-title
                        ><v-card-subtitle class="pl-0 pt-0 pb-0">{{
                          sessionSet.spaker
                        }}</v-card-subtitle>
                        <p>{{ sessionSet.duringTime }}</p>
                      </v-col>
                    </v-row>
                    <hr
                      v-if="
                        sessionSet !==
                        session.sessionSet[session.sessionSet.length - 1]
                      "
                      class="mb-0"
                    />
                  </v-card-text>
                </div>
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
  asyncData({ store }) {
    // apis
    return {
      agenda: store.getters.getAgenda,
    }
  },
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
  color: 4d4d4d;
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
    .v-card__text + .v-card__text {
      padding-top: 0 !important;
    }
  }
  hr {
    width: 100%;
    margin: 15px auto 0;
    height: 1px;
    background: #bdbdbd;
    border: 0;
  }
}
</style>
