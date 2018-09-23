<template>
  <v-card contextual-style="white text-dark">
    <div slot="header">
      {{ $t('general.public_information') }}
      <p class="description">Information provided bellow will visible to your customers.
        Use this to provide support specific contact information.</p>
    </div>
    <div slot="body">
      <el-form ref="form" :model="form" label-width="220px" size="medium">
        <el-form-item label="Business name">
          <el-input v-model="form.businessName"></el-input>
        </el-form-item>

        <el-form-item label="Website">
          <el-input v-model="form.website"></el-input>
        </el-form-item>

        <el-form-item label="Legal name">
          <el-input v-model="form.legalName"></el-input>
          <p>This may be the legal entity name, or a trade name</p>
        </el-form-item>

        <el-form-item label="Support site">
          <el-input v-model="form.supportSite"></el-input>
        </el-form-item>

        <el-form-item label="Customer support phone number">
          <el-input placeholder="+8 888 888 88 88" v-model="form.customerSupportNumber"></el-input>
        </el-form-item>

        <el-form-item label="Address">
          <el-select v-model="form.address.country" placeholder="Country">
            <el-option
              v-for="item in 20"
              :key="item"
              :label="item"
              :value="item">
            </el-option>
          </el-select>
        </el-form-item>

        <el-form-item>
          <el-input placeholder="Address line 1" v-model="form.address.firstAddress"></el-input>
        </el-form-item>

        <el-form-item>
          <el-input placeholder="Address line 2" v-model="form.address.secondAddress"></el-input>
        </el-form-item>

        <el-form-item>
          <el-input placeholder="City" v-model="form.address.city"></el-input>
        </el-form-item>

        <el-form-item>
          <el-input placeholder="State / Region" v-model="form.address.region"></el-input>
        </el-form-item>

        <el-form-item>
          <el-input placeholder="Postal code" v-model="form.address.postalCode"></el-input>
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
    name: "PublicInformation",
    data() {
      return {
        form: {
          businessName: '',
          website: '',
          legalName: '',
          supportSite: '',
          email: '',
          customerSupportNumber: '',
          address: {
            country: '',
            firstAddress: '',
            secondAddress: '',
            city: '',
            region: '',
            postalCode: ''
          }
        }
      }
    },
    components: {
      VCard,
    },
  }
</script>

<style scoped>
  .description {
    font-size: 15px;
  }
</style>
