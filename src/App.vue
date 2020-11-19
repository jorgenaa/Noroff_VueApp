<template>
	<div id="app">
		<Recipes :recipes="recipes" /> 
	</div>
</template>

<script>
import Recipes from './components/Recipes.vue';

export default {
	name: 'App',
	components: { 
     Recipes
    
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
