<template>
	<div id="app">
		<Header />
		<Recipes :recipes="recipes" />

		{{ sort() }}
		<Footer />
	</div>
</template>

<script>
import Header from './components/Layout/Header';
import Recipes from './components/Recipes.vue';
import Footer from './components/Layout/Footer';

export default {
	name: 'App',
	components: {
		Header,
		Recipes,
		Footer,
	},
	props: ['recipes'],

	created() {
		const url = 'http://www.recipepuppy.com/api/';

		fetch(url)
			.then(res => res.json())
			.then(data => {
				this.recipes = data.results;
			})
			.catch(err => console.log(err));
	},
	methods: {
		sort() {
			this.recipes.sort((a, b) => (a > b ? 1 : -1));
		},
	},
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	color: #2c3e50;
}
</style>
