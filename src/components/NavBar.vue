<template>
  <section class="navbar">
    <div class="logo">mango</div>
    <div class="menu-items" :class="{ 'collapse-menu': collapse }">
      <div class="menu-item" v-for="(navItem, index) in navItems" :key="index">
        <span>{{ navItem }}</span>
      </div>
    </div>
    <i
      class="fa fa-bars fa-2x navigation-icon"
      v-if="!collapse"
      @click="handleCollapse"
    ></i>
    <i
      class="fa fa-times fa-2x navigation-icon"
      v-else
      @click="handleCollapse"
    ></i>
  </section>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      navItems: ["menu item 1", "menu item 2", "menu item 3", "menu item 4"],
      collapse: false,
    };
  },
  methods: {
    handleCollapse() {
      this.collapse = !this.collapse;
    },
  },
};
</script>

<style lang="scss" scoped>
.navbar {
  height: 88px;
  background: $dark-gray;
  z-index: 1;
  @apply fixed top-0 right-0 left-0 flex justify-between items-center;

  .logo {
    width: 30%;
    background: $dark-blue;
    color: $white;
    font-weight: 700;
    font-size: 36px;
    @apply flex items-center uppercase pl-12 h-full;
    @include tablet {
      font-size: 26px;
      width: 25%;
    }
    @include mobile {
      padding-left: 20px;
    }
  }
  .menu-items {
    @apply flex pr-12;
    @include tablet {
      @apply pl-7;
    }

    .menu-item {
      font-weight: 500;
      font-size: 16px;
      color: $white;
      margin-right: 50px;
      @apply uppercase;
      @include tablet {
        font-size: 12px;
        @apply pr-0;
      }
    }

    @include mobile {
      display: none;

      &.collapse-menu {
        background: $dark-blue;
        display: block;
        position: absolute;
        left: 0;
        right: 0;
        top: 88px;
        padding: 12px 50px;

        .menu-item {
          padding: 8px 0;
        }
      }
    }
  }

  .navigation-icon {
    display: none;
    margin-right: 20px;
    color: $white;
    cursor: pointer;

    @include mobile {
      display: block;
    }
  }

  @include mobile {
    background: $dark-blue;
  }
}
</style>
