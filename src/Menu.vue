<template>
  <div class="menu">
    <div v-if="visible">
	  test
	</div>
	<button @click="toggle"></button>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        visible: true
      }
    },
    methods: {
      toggle: function () {
	    this.visible = !this.visible
	  }
    }
  }
</script>

<style>

</style>
