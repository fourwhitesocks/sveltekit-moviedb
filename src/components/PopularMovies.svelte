<script>
	export let popular;
	//below console.log shows all popular movies ~ in this case the index of first one
	console.log(popular[0]);
	//shows what we can pull from object
	import MovieCard from './MovieCard.svelte';
</script>

<h3>Popular Movies</h3>
<div class="popular-movies">
	{#each popular as movie}
		<!-- we came up with 'movie above' so you use that and then pull out the title -->
		<MovieCard {movie} />
	{/each}
</div>

<style>
	h3 {
		padding: 0 1rem;
	}

	.popular-movies {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 1rem;
		grid-row-gap: 2rem;
	}
</style>
