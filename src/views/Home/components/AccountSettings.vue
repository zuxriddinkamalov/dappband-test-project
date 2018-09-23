<template>
  <v-card contextual-style="white text-dark">
      <span slot="header">
        {{ $t('general.account_settings') }}
      </span>
    <div slot="body">
      <el-form ref="form" :model="form" label-width="220px" size="medium">
        <el-form-item label="Business account name">
          <el-input v-model="form.accountName"></el-input>
        </el-form-item>

        <el-form-item label="Business verification">
          <el-tag>Verified</el-tag>
        </el-form-item>

        <el-form-item label="Business representative verification">
          <el-button type="primary">Verify</el-button>
        </el-form-item>
      </el-form>

    </div>
    <div slot="footer">
      <div class="pull-right">
        <el-button>Cancel</el-button>
        <el-button type="primary">Save</el-button>
      </div>
    </div>
  </v-card>
</template>

<script>
  import VCard from '@/components/Card.vue';

  export default {
    name: "AccountSettings",
    data() {
      return {
        form: {
          accountName: '',
        }
      }
    },
    components: {
      VCard,
    },
  }
</script>

<style scoped>

</style>
