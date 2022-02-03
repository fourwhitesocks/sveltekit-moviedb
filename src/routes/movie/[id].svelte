<script context="module">
	export async function load({ fetch, params }) {
		//console.log(params);
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=607fde241833693a326fc7fcd4553811&language=en-US`
		);
		const movieDetail = await res.json();
		//console.log(data);
		if (res.ok) {
			return {
				//returns the object
				props: { movieDetail }
			};
		}
	}

	//607fde241833693a326fc7fcd4553811
</script>

<script>
	export let movieDetail;
	//can extract any other info from below console.log/movidDetail and concatinate it afer movieDetail
	console.log(movieDetail);
</script>

<h1>stopped 54.57</h1>
<div class="movie-details">
	<div class="img-container">
		<img
			src={'https://image.tmdb.org/t/p/original' + movieDetail.backdrop_path}
			alt={movieDetail.title}
		/>
	</div>
	<div class="txt-contaier">
		<h1>{movieDetail.title}</h1>
		<h2>{movieDetail.tagline}</h2>

		<p>
			<span> Release Date: </span>{movieDetail.release_date} <br />
			<!-- little confusing but the $ below is not for an expression it is for actually money  -->
			<span>Budget: </span> ${movieDetail.budget}<br />
			<span>Rating:</span>{movieDetail.vote_average}<br />
			<span>Runtime:</span>{movieDetail.runtime}mins
		</p>
	</div>
</div>

<style>
	h1 {
		padding: 1rem 0rem 2rem;
	}

	p {
		padding: 1rem 0rem;
	}

	.img-container {
		width: 100;
	}
	img {
		width: 100%;
		border-radius: 1rem;
	}
	.movie-details {
		margin: 2rem 20%;
	}

	span {
		font-weight: bold;
	}
</style>
