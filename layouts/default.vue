<template>
  <v-app>
    <nuxt></nuxt>
    <Dialog />
  </v-app>
</template>
<script>
import Dialog from '~/components/dialog'
export default {
  components: {
    Dialog,
  },
}
</script>

<style lang="scss">
.v-application {
  font-family: 'Dancing Script', cursive;
}

.v-toolbar__title {
  text-align: center;
  width: 100%;
  font-weight: bold;
}

.v-application .primary {
  background-color: #1a56be !important;
  border-color: #1a56be !important;
}

.text-primary {
  color: #1a56be;
  font-weight: bold;
}

.text-title {
  font-size: 20px;
}
.w-100 {
  width: 100%;
}
.my-btn {
  font-size: 20px !important;
  text-transform: none !important;
  height: auto;
  padding: 10px 0 !important;
  font-weight: bold;
  min-height: 50px;
  &.outlined {
    border: 1px solid #1a56be;
    border-radius: 28px;
    line-height: normal;
  }
}

.set-pading {
  padding: 0 10px;
}
</style>
