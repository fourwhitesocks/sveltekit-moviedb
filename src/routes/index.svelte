<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=607fde241833693a326fc7fcd4553811&language=en-US&page=1`
		);
		const data = await res.json();
		//console.log(data);
		if (res.ok) {
			return {
				//the first part popular is any name we want
				props: { popular: data.results }
			};
		}
	}

	//607fde241833693a326fc7fcd4553811
</script>

<script>
	import PopularMovies from '../components/PopularMovies.svelte';

	export let popular;
</script>

<section>
	<!-- shorthand:  if you name popular the same in both you can format it like the bottom long version is shown first 
	<PopularMovies movies={popular} /> -->
	<PopularMovies {popular} />
</section>
