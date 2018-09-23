<template>
  <div class="wrapper container">
    <nav class="navbar navbar-expand-lg bg-transparent">

      <button
        class="navbar-toggler"
        type="button"
        @click="toggleMenu"
      >
        <span class="navbar-toggler-icon"/>
      </button>

      <div
        :class="{ show : menuCollapsed}"
        class="collapse navbar-collapse"
      >
        <ul class="navbar-nav mr-auto">
          <a class="nav-link">
            <el-input
              class="search"
              placeholder="Search">
              <i slot="prefix" class="el-input__icon el-icon-search"></i>
            </el-input>
          </a>
        </ul>
        <div class="navbar-text profile-button" :style="{
          'background-image': 'url(img/logo.png)'
        }"></div>
      </div>
    </nav>

    <div class="container pt-4">
      <div class="row">
        <div class="col col-12">
          <!-- Content will be placed here -->
          <slot/>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
/* ============
 * Default Layout
 * ============
 *
 * Used for the home and account pages.
 *
 * Layouts are used to store a lot of shared code.
 * This way the app stays clean.
 */

export default {
  /**
   * The name of the layout.
   */
  name: 'DefaultLayout',

  /**
   * The data that can be used by the page.
   *
   * @returns {Object} The view-model data.
   */
  data() {
    return {
      menuCollapsed: false,
    };
  },

  /**
   * The methods that the layout can use.
   */
  methods: {
    /**
     * Will log the user out.
     */
    logout() {
      this.$store.dispatch('auth/logout');
    },

    /**
     * Will toggle the menu.
     */
    toggleMenu() {
      this.menuCollapsed = !this.menuCollapsed;
    },
  },
};
</script>

<style lang="less">
  .pt-4 {
    padding-bottom: 50px;
  }
  .search {
    width: 400px!important;
    max-width: 100%;
  }
  .profile-button {
    width: 30px;
    height: 30px;
    background-size: cover;
  }
</style>
