<template>
  <div>
    <v-app-bar color="primary" dense flat dark>
      <v-toolbar-title>Register</v-toolbar-title>
    </v-app-bar>
    <v-container class="pt-0 pb-0">
      <v-row>
        <v-col cols="12">
          <div class="mt-8 text-primary text-title text-center">
            Step 2 of 2
          </div>
        </v-col>
        <v-col cols="12">
          <v-form>
            <p class="text-center text-title mb-0 mt-4">
              Tell us more a bit ...
            </p>
            <v-text-field
              v-model="form.email"
              label="Email"
              dense
              required
            ></v-text-field>
            <v-text-field
              v-model="form.phone"
              label="Phone"
              dense
              required
            ></v-text-field>
            <v-dialog ref="dialog" v-model="modal" persistent width="290px">
              <template v-slot:activator="{ on, attrs }">
                <v-text-field
                  v-model="form.birthday"
                  label="Birthday"
                  prepend-icon="event"
                  readonly
                  v-bind="attrs"
                  class="set-birthday"
                  v-on="on"
                ></v-text-field>
              </template>
              <v-date-picker
                v-model="form.birthday"
                :max="new Date().toISOString().substr(0, 10)"
                scrollable
              >
                <v-spacer></v-spacer>
                <v-btn text color="primary" @click="modal = false"
                  >Cancel</v-btn
                >
                <v-btn text color="primary" @click="$refs.dialog.save(date)"
                  >OK</v-btn
                >
              </v-date-picker>
            </v-dialog>
            <p class="text-center text-title mb-0 mt-4">
              Work Profile
            </p>
            <v-text-field
              v-model="form.company"
              label="Company"
              dense
              required
            ></v-text-field>
            <v-text-field
              v-model="form.position"
              label="Position"
              dense
              required
            ></v-text-field>
            <v-btn
              rounded
              color="primary w-100 mt-10 my-btn"
              dark
              @click="register"
              >Register</v-btn
            >
            <div class="w-100 text-center my-btn text-primary" @click="back">
              Back
            </div>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      form: {
        email: '',
        phone: '',
        birthday: new Date().toISOString().substr(0, 10),
        company: '',
        position: '',
      },
      modal: false,
    }
  },
  methods: {
    register() {
      console.log('registetr')
    },
    back() {
      this.$router.push('/register')
    },
  },
}
</script>
<style lang="scss" scoped>
.v-form {
  padding: 0 10px;
}
.set-birthday {
  position: relative;
  ::v-deep .v-input__prepend-outer {
    position: absolute;
    right: 0;
  }
}
</style>
