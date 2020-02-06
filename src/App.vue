
<script lang="ts">
	import Vue from 'vue'
	import { distance } from '@/util'

	export default Vue.extend({
		name: 'app',
		data(): {
			eyeball?: SVGCircleElement
		} {
			return {}
		},
		mounted() {
			this.eyeball = this.$refs.eyeball as SVGCircleElement
			addEventListener('mousemove', this.moveEyeball)
		},
		methods: {
			moveEyeball(e: MouseEvent) {
				if (!this.eyeball) return
				const rect = this.eyeball.getBoundingClientRect() as DOMRect
				if (!rect) return

				const x = rect.x + (36.74 / 2)
				const y = rect.y + (36.74 / 2)

				const stretchLimit = 250

				const absDist = distance(e.x, e.y, x, y)
				const percentDist = (absDist > stretchLimit ? stretchLimit : absDist) / stretchLimit

				const yOffset = percentDist * 30

				const radian = Math.atan2(e.pageX - x, e.pageY - y)
				const deg = (radian * (180 / Math.PI) * -1)

				const xOrigin = this.eyeball.cx.baseVal.value
				const yOrigin = this.eyeball.cy.baseVal.value

				const transformAttr = `translate(0,${yOffset}) rotate(${deg}, ${xOrigin}, ${yOrigin - yOffset})`
				this.eyeball.setAttribute('transform', transformAttr)
			},
		},
	})
</script>

<template>
	<div id='app'>
		<div id='logo-space'>
			<svg id='logo' viewBox='120.055 86.526 260.074 326.59' xmlns='http://www.w3.org/2000/svg' xmlns:bx='https://boxy-svg.com'>
				<defs>
					<bx:grid x='120.055' y='86.526' width='260.074' height='326.59' />
				</defs>
				<path d='M 790.4 423.2 m -129.003 0 a 129.003 129.003 0 1 0 258.006 0 a 129.003 129.003 0 1 0 -258.006 0 Z M 790.4 423.2 m -64.501 0 a 64.501 64.501 0 0 1 129.002 0 a 64.501 64.501 0 0 1 -129.002 0 Z' style='' transform='matrix(1, 0.000079, -0.000079, 1, -540.366392, -139.864531)' bx:shape='ring 790.4 423.2 64.501 64.501 129.003 129.003 1@68f4b763' />
				<rect x='120.987' y='87.5' width='64.643' height='325' rx='32.3' ry='32.3' />
				<rect x='314.37' y='87.5' width='64.643' height='325' rx='32.3' ry='32.3' />
				<circle ref='eyeball' id='eyeball' cx='250' cy='283.379' r='30' />
			</svg>
			<h1>lost design</h1>
		</div>
		<div id='main'>
			<!-- <nav>
				<router-link to='/'>Home</router-link>
				<router-link to='/portfolio'>My Portfolio</router-link>
			</nav> -->
			<router-view/>
		</div>
	</div>
</template>

<style>
@import url('https://fonts.googleapis.com/css?family=Nunito:300,400,700&display=swap');

:root {
	font-family: 'Nunito', sans-serif;
	--blue: rgb(152, 191, 218);
	--tan: rgb(221, 209, 180);
	--light-blue: rgb(207, 227, 240);
	--lighter-blue: rgb(236, 244, 250);
}

body {
	margin: 0;
	background-color: var(--blue);
}

#app {
	display: flex;
	height: 100vh;
	width: 100vw;
}

#app > div {
	flex: 1;
}

#logo-space {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
}

#logo-space > h1 {
	color: var(--light-blue);
}

#logo {
	height: 200px;
	fill: var(--tan);
}

#eyeball {
	transition: fill 1s;
	fill: var(--light-blue);
}

#eyeball:hover {
	fill: var(--lighter-blue);
}

a {
	color: var(--light-blue);
}
</style>
