<template>
  <div>
    <v-app-bar color="primary" dense flat dark>
      <v-toolbar-title>Register</v-toolbar-title>
    </v-app-bar>
    <v-container class="pt-0 pb-0">
      <v-row>
        <v-col cols="12">
          <div class="mt-8 text-primary text-title text-center">
            Step 1 of 2
          </div>
        </v-col>
        <v-col cols="12" class="text-center pb-0">
          <img src="~/assets/profile.png" alt="" width="155" />
        </v-col>
        <v-col cols="12" class="text-center pt-2 pb-0">
          Display Name
        </v-col>
        <v-col cols="12">
          <v-form>
            <v-text-field
              v-model="form.firstName"
              label="firstName"
              required
            ></v-text-field>
            <v-text-field
              v-model="form.lastName"
              label="lastName"
            ></v-text-field>
            <div class="gender-group d-flex mt-3">
              <p>Gender</p>
              <div
                class="circle"
                :class="form.gender == 1 ? 'active' : ''"
                @click="chooseGender(1)"
              >
                <svg
                  id="Capa_1"
                  enable-background="new 0 0 512 512"
                  height="32"
                  viewBox="0 0 512 512"
                  width="25"
                  xmlns="http://www.w3.org/2000/svg"
                  color="#fff"
                >
                  <g>
                    <path
                      d="m411 155c0-85.467-69.533-155-155-155s-155 69.533-155 155c0 80.407 61.545 146.702 140 154.272v102.728h-55c-8.284 0-15 6.716-15 15s6.716 15 15 15h55v55c0 8.284 6.716 15 15 15s15-6.716 15-15v-55h55c8.284 0 15-6.716 15-15s-6.716-15-15-15h-55v-102.728c78.455-7.57 140-73.865 140-154.272zm-280 0c0-68.925 56.075-125 125-125s125 56.075 125 125-56.075 125-125 125-125-56.075-125-125z"
                    />
                  </g>
                </svg>
              </div>
              <p @click="chooseGender(1)">Female</p>
              <div
                class="circle"
                :class="form.gender == 2 ? 'active' : ''"
                @click="chooseGender(2)"
              >
                <svg
                  id="Capa_1"
                  enable-background="new 0 0 512 512"
                  height="32"
                  viewBox="0 0 512 512"
                  width="25"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <g>
                    <path
                      d="m497 0h-140c-8.284 0-15 6.716-15 15s6.716 15 15 15h103.787l-173.104 173.104c-31.503-26.601-70.975-41.104-112.683-41.104-46.744 0-90.69 18.203-123.744 51.256s-51.256 77-51.256 123.744 18.203 90.69 51.256 123.744 77 51.256 123.744 51.256 90.69-18.203 123.744-51.256 51.256-77 51.256-123.744c0-41.708-14.503-81.18-41.104-112.683l173.104-173.104v103.787c0 8.284 6.716 15 15 15s15-6.716 15-15v-140c0-8.284-6.716-15-15-15zm-219.469 439.531c-27.387 27.386-63.8 42.469-102.531 42.469s-75.144-15.083-102.531-42.469c-27.386-27.387-42.469-63.8-42.469-102.531s15.083-75.144 42.469-102.531c27.387-27.386 63.8-42.469 102.531-42.469s75.144 15.083 102.531 42.469c27.386 27.387 42.469 63.8 42.469 102.531s-15.083 75.144-42.469 102.531z"
                    />
                  </g>
                </svg>
              </div>
              <p @click="chooseGender(2)">Male</p>
            </div>
            <v-btn rounded color="primary w-100 mt-10 my-btn" dark @click="next"
              >Next</v-btn
            >
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
        firstName: this.$store.getters.getRegister.firstName,
        lastName: this.$store.getters.getRegister.lastName,
        gender: this.$store.getters.getRegister.gender,
      },
    }
  },
  methods: {
    chooseGender(gender) {
      this.form.gender = gender
    },
    validate() {
      let validated = true
      const errors = []
      const validatorField = ['firstName', 'lastName']
      validatorField.forEach((field) => {
        if (this.form[field] === '') {
          validated = false
          errors.push(`${field} can not be null`)
        }
      })
      if (!validated) {
        this.$store.dispatch('setDialog', {
          isShow: true,
          title: 'Form is errors',
          message: errors.map((err) => err + '<br/>').join(''),
        })
      }
      return validated
    },
    next() {
      if (this.validate()) {
        this.$store.dispatch('setRegister', this.form)
        this.$router.push('register/step2')
      }
    },
  },
}
</script>
<style lang="scss" scoped>
.v-form {
  padding: 0 10px;
}
.gender-group p {
  margin-bottom: 0;
  align-self: center;
  margin-right: 20px;
}
.circle {
  width: 45px;
  height: 45px;
  color: #fff;
  border-radius: 50%;
  position: relative;
  background: rgba($color: #000000, $alpha: 0.3);
  margin-right: 7px;
  &.active {
    background: #1a56be;
  }
  svg {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
}
</style>
