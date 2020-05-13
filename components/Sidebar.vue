<template>
  <nav id="sidebar" class="sidebar" :class="dataToggle ? 'active' : ''">
    <div class="sidebar__burger" @click="toggle()">
      <img :src="dataToggle ? cross : navbar" alt style="width: 20px;">
    </div>
    <div class="sidebar__header d-flex">
      <a>
        <img src="@/assets/images/Logo/gamespace-01.png" class="sidebar__logo">
      </a>
    </div>
    <ul class="list-unstyled sidebar__components">
      <li>
        <nuxt-link to="/" exact>
          Home
        </nuxt-link>
        <nuxt-link to="/leaderboard">
          Leaderboard
        </nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: { dataToggle: Boolean },
  data () {
    return {
      navbar: require('@/assets/images/Icon/navbar.svg'),
      cross: require('@/assets/images/Icon/cross.svg')
    }
  },
  methods: {
    toggle () {
      this.$emit('action')
    }
  }
}
</script>
