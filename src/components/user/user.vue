<template>
  <div :class="['profile-info', sizeClass]">
    <div class="profile-img">
      <img
      :src="avatar"
      alt="avatar"
      class="profile-avatar-img">
    </div>
    <div class="data">
      <div class="profile-name">{{ username }}</div>
      <div class="type" v-if="type.length">{{ type.toLowerCase() }}</div>
    </div>
  </div>
</template>

<script>
import { sizes } from './enums'
export default {
  data () {
    return {
      sizeClass: `size-${this.size}`
    }
  },
  props: {
    avatar: {
      type: String,
      required: true
    },
    username: {
      type: String,
      required: true
    },
    type: {
      type: String,
      default: ''
    },
    size: {
      type: String,
      default: sizes.small
    }
  }
}
</script>

<style src="./user.scss" lang="scss" scoped></style>
