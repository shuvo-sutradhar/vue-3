<template>
	{{ val }}
</template>

<script>
import { customRef } from 'vue'

const isemail = value => value.includes('@');

export default {


	setup() {

		const email = customRef((track, trigger) => {
			let value = null;

			return {
				get() {
					track()
					return value
				},
				set(input) {
					if(isemail(input)) {
						value = input
						trigger();
					}
				}
			}
		})

		email.value = 'invalid'
		console.log(email.value);
		email.value = 'test@g.com'
		console.log(email.value);

	}

}

</script>