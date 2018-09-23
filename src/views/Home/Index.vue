<template>
  <v-layout>
    <div class="forms">
      <account-settings />
      <public-information />
    </div>
  </v-layout>
</template>

<script>
/* ============
 * Home Index Page
 * ============
 *
 * The home index page.
 */

import VLayout from '@/layouts/Default.vue';
import AccountSettings from './components/AccountSettings.vue';
import PublicInformation from './components/PublicInformation.vue';

export default {
  /**
   * The name of the page.
   */
  name: 'HomeIndex',

  /**
   * The components that the page can use.
   */
  components: {
    VLayout,
    AccountSettings,
    PublicInformation,
  },
};
</script>

<style>
  .forms>div {
    margin-bottom: 30px;
  }
  .forms>div:last-child {
    margin-bottom: 0;
  }
</style>
