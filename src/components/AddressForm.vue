<template>
  <div>
    <div class="item">
      <label>Country: {{value.country}}</label>
      <input 
        type="text" 
        :value="value.country" 
        @input="onChangeCountry($event.target.value)"
      />
      <label>Street: {{value.street}}</label>
      <input 
        type="text" 
        :value="value.street" 
        @input="onChangeStreet($event.target.value)"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: 'AddressForm',

props: {
    value: {
      type: Object,
      required: true
    }
  },

  methods: {
    onChangeCountry (value) {
      const updatedValue = {...this.value, country: value};
      console.log('this.value', this.value)
      console.log('updatedValue', updatedValue)
      this.$emit('input', updatedValue);
    },
    onChangeStreet (value) {
      const updatedValue = {...this.value, street: value};
      this.$emit('input', updatedValue);
    }    
  }


}
</script>

<style>
</style>