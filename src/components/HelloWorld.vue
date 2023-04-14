<template>
  <div class="hello">
    <button @click="showModal = true">Click</button>
    {{showModal}}
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      showModal: false
    }
  },

  props: {
    msg: String
  }
}
</script>
