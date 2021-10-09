

<template>
	<button :class="{ 'dark-mode' : settings.theme === 'dark' }" @click="toggleMode">
		Switch to {{ oppsiteTheme }} mode
	</button>
</template>


<script>

	import { inject, computed } from 'vue'
	export default {
		setup() {
			const settings = inject('settings')

			const oppsiteTheme = computed(() => 
				settings.theme === 'dark' ? 'light' : 'dark'
			)

			const toggleMode = () => {
				settings.theme = oppsiteTheme.value
			}
			return { settings, oppsiteTheme, toggleMode }
		} 
	}
</script>


<style scoped>
.dark-mode {
	color: white;
	background-color: black;
}
</style>