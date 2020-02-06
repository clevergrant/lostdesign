<template>
	<div id='home'>
		<!-- <HelloWorld msg='Welcome to Your Vue.js App'/> -->
		<h1>&lt;this site is under construction&gt;</h1>

		<h3><a href='http://fireemblem.lostdesign.dev' target='_blank' rel='noopener noreferrer'>In the meantime, check this out</a></h3>

	</div>
</template>

<script>
	import HelloWorld from '@/components/HelloWorld.vue'

	export default {
		name: 'home',
		// components: {
		// 	HelloWorld,
		// },
	}
</script>

<style scoped>
#home {
	display: flex;
	flex-direction: column;

	justify-content: center;
	align-items: center;

	height: 100vh;
}

#home > h1 {
	color: var(--light-blue);
}
</style>