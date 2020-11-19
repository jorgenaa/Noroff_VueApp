<template>
	<div class="container" >
		<div class="recipe-card" v-for="recipe in recipes" :key="recipe.title">
			<a :href="recipe.href" :title="titleMsg"><h3>{{ recipe.title }}</h3></a>
			<a :href="recipe.href" :title="titleMsg"><img :src="recipe.thumbnail" /></a>
			<p><span>Ingredients:</span>{{ recipe.ingredients }}</p>
		</div>
	</div>
</template>

<script>

export default {
	name: 'Recipes',
	data(){
		return {
			titleMsg: "For fully description click here"
		}
	},
	
    props: ['recipes']
   
};
</script>

<style scoped>
.container {
    margin: 0 auto;
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
