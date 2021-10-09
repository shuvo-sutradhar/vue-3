<template>
	<ThemeButton />
</template>


<script>
	import {  provide, reactive, watch } from 'vue'
	import ThemeButton from './ThemeButton.vue'

	export default {
		//"no-mixed-spaces-and-tabs": 0,
		components: {
		    ThemeButton
		  },
		setup() {


			const settings = reactive({
				theme: 'light'
			})

			//The provide API is a function we use to define the data we want to be passed down to a child component.
			provide('settings', settings); 

			watch(settings, settings => {
				console.log(`SettingsProvider: theme has been switched to ${settings.theme} mode.`)
			})

		} 
	}
</script>

<style scoped>
	
</style>