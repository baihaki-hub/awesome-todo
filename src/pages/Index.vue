<template>
  <q-page padding>
    <input v-model="message" @keyup="handleKeyup"
	  @mouseleave="alertMessage"
	/>
	<button @click="clearMessage">Clear</button>
    <h5 
	    v-if="message.length" class="border-grey">{{ message }}</h5>
	<h6 v-else>No Message Entered</h6>
  </q-page>
</template>

<script>
  export default {
    data() {
	  return {
		message: 'I love Vue.js'
	  }
	},
	methods: {
	  clearMessage() {
		this.message = ''
	  },
	  handleKeyup(e) {
		console.log(e)
		if (e.keyCode == 27) {
			this.clearMessage()
		}
		else if (e.keyCode == 13) {
			this.alertMessage()
		}
	  },
	  alertMessage() {
		alert(this.message)
	  }
	}
  }
</script>

<style>
  .border-grey {
	  border: 1px solid grey;
  }
</style>