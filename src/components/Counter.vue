<template>
	<button @click="increment">Counter</button>

	<div style="padding: 10px; margin-top: 10px">{{ counter }}</div>
	<div>{{ arrayOfEmojis }}</div>
</template>

<script>
import { ref, onMounted, watch, computed } from 'vue'
export default {
	
	props: {
		emoji: { type: String, default: '💖' }
	},


	setup(props) {

		onMounted(() => {
			// console.log("Counter component has been mounted!");
		})

		const counter = ref(0);
		const increment = () => counter.value++;

		watch(counter, (current) => {
			if(current === 5) { console.log('You have clicked 5 time.') }
		})

		const arrayOfEmojis = computed(() => {
			return Array.from(new Array(counter.value), () => props.emoji).join(' ');
		})

		return { 
			counter, 
			increment,
			arrayOfEmojis
		}

	}

}

</script>