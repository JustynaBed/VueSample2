<template>
  <div class="hello">
    <button @click="showModal = true">Open Modal</button>
    <CustomModal 
      @close="showModal = false"
      v-if=showModal
    >
      <template #header>
        <h2>Address</h2>
      </template>
      <template #body>
        <AddressForm
          v-model="address"
        ></AddressForm>
      </template>
    </CustomModal>
    <div class="item">address.country: {{address.country}}</div>
    <div class="item">address.street: {{address.street}}</div>
  </div>
</template>

<script>
import CustomModal from './CustomModal.vue'
import AddressForm from './AddressForm.vue'

export default {
  name: 'HelloWorld',
  data () {
    return {
      showModal: false,
      address: {
        country: '',
        street: ''
      }
    }
  },

  props: {
    msg: String
  },

  components: {
    CustomModal,
    AddressForm    
  }
}
</script>

<style>
.item {
  margin: 10px;
}
</style>
