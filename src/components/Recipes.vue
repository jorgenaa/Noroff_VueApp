<template>
	<div class="container" >
		<div class="recipe-card" v-for="recipe in recipes" :key="recipe.title">
			<a :href="recipe.href"><h3>{{ recipe.title }}</h3></a>
			<img :src="recipe.thumbnail" />
			<p><span>Ingredients:</span>{{ recipe.ingredients }}</p>
		</div>
	</div>
</template>

<script>

export default {
    name: 'Recipes',
    props: ['recipes']
   
};
</script>

<style scoped>
.container {
    margin: 60px auto;
    max-width: 1200px; 
	display: flex;
	flex-wrap: wrap;
}

.recipe-card {
	flex-basis: 300px;
	margin: 16px;
	padding: 16px;
	border: 1px solid black;
  border-radius: 5px;
}
h3 {
  font-size: 22px;
}
a {
  text-decoration: none;
  color: green;
}
p {
  font-size: 16px;
  letter-spacing: 0.5;
  line-height: 1.5;
}

span {
	font-weight: bold;
	padding-right: 10px;
}

img {
	width: 100%;
  
}
</style>
