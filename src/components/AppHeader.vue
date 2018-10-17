<template>
  <header role="banner"
          itemscope
          itemtype="http://schema.org/WPHeader">
    <app-logo />
    <app-nav />
  </header>
</template>

<script>
import AppNav from '@components/AppNav'
import AppLogo from '@components/AppLogo'

export default {
  components: { AppNav, AppLogo }
}
</script>

<style lang="scss" scoped>
.desktop-nav {
    display: none;
  
  @media (min-width: 900px) {
    display: block;
  }
  &-list {
    margin-bottom: 0;
    display: flex;
  }
  &-item {
    list-style-type: none;
    margin-bottom: 0;
  }
}

.drawerToggle {
  -webkit-appearance: none;
  cursor: pointer;
  background: white;
  border: none;
  font-size: 1em;
  font-weight: 400;
  font-family: Vollkorn, sans-serif;
  position: relative;
  z-index: 9;
}
  @media (min-width: 900px) {
    .drawerToggle, .v-menu-button {
      display: none;
    }
  }
header {
  display: flex;
  align-items: center;
  justify-content: space-around;
  justify-content: space-between;
  padding: 0 1.25em;
  .logo {
    width: 125px;
    margin: 0;
  }
}

nav {
  a {
    color: white;
    margin: 0.25em 0.75em;
  }
}
</style>
