<template>
	{{ val }}
</template>

<script>
import { toRefs } from 'vue'
export default {

	props: {
		a: { type: Number, default: 0 },
		b: { type: String, default: 'Vue 3!' },
		c: { type: Boolean, default: true }
	},

	setup(props) {

		// const val2 = ref({ data: 1 });
		// console.log(val2.value.data);

		// const obj = reactive({ data: 0 });		
		// console.log(obj.data);

		const { a,b, c } = toRefs(props);
		console.log(a.value);
		console.log(b.value);
		console.log(c.value);

	}

}

</script>