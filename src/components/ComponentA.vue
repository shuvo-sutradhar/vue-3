<template>
	<div class="card text-center">
		Component A
		<br>

		<button type="text" @click="toggle = !toggle">Click</button>
		<teleport to="#endofbody" :disabled="toggle">

			<p>Text from component A</p>

		</teleport>

		<button type="text" @click="toggle2 = !toggle2">Click2</button>
		<teleport to="#endofbody" :disabled="toggle2">

			<p>Text from component A</p>

		</teleport>
	</div>
</template>

<script>
	
import { ref } from 'vue'
export default {
	setup() {
		return { toggle: ref(false), toggle2: ref(false) }
	}
}

</script>

<style type="text/css">
	
.card{
	border: 1px solid #000;
	width: 300px;
	margin: auto;
	overflow: hidden;
}

</style>