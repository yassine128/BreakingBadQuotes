<script>
	const url = 'https://api.breakingbadquotes.xyz/v1/quotes';
	let author; 
	let quote; 
	let backGroundImage = ''; 

	fetch(url)
		.then((response) => {
			return response.json();
		})
		.then((data) => {
			let APIinfo = data; 
			author = APIinfo[0].author; 
			quote = APIinfo[0].quote;

			if (quote.length >= 150) {
				location.reload();
			}
			
			switch(author) {
				case 'Hank Schrader': backGroundImage = 'https://www.hollywoodreporter.com/wp-content/uploads/2020/03/bcs_503_gl_0514_0595_rt-h_2020.jpg?w=1296'; break;
				case 'Jesse Pinkman': backGroundImage = 'https://images.immediate.co.uk/production/volatile/sites/3/2019/10/breaking-bad-jesse-11b6c49.jpg'; break;
				case 'Walter White': backGroundImage = 'https://www.indiewire.com/wp-content/uploads/2018/07/breakingbadformon_wide-22d0f0aa716956d518b391936d3bc323dd7a3848-s900-c85.jpg'; break; 
				case 'The fly': backGroundImage = 'https://m.media-amazon.com/images/M/MV5BZWFkNDIwMGItYzg0MS00NDc4LWI1MmItZTlmYWYzYjA5NWYyXkEyXkFqcGdeQXVyNTMyMDkwMTE@._V1_.jpg'; break;
				case 'Saul Goodman': backGroundImage = 'https://cdn.mos.cms.futurecdn.net/SMFbNxm87tUwivBHAFKGAJ.jpg'; break;
				case 'Gus Fring': backGroundImage = 'https://i.ytimg.com/vi/JXMIpHDgb2A/maxresdefault.jpg'; break;
				case 'Walter White Jr': backGroundImage = 'https://mixmag.net/assets/uploads/images/_ampPreview/walter-white-jr.jpg'; break;
				case 'Gustavo Fring': backGroundImage = 'https://i.ytimg.com/vi/JXMIpHDgb2A/maxresdefault.jpg'; break;
				case 'Mike Ehrmantraut': backGroundImage = 'https://static01.nyt.com/images/2022/08/18/arts/16saul-banks/16saul-banks-videoSixteenByNine3000.jpg'; break;
				case 'Skyler White': backGroundImage = 'https://www.looper.com/img/gallery/the-reason-skyler-white-was-the-most-hated-character-on-breaking-bad/intro-1582563946.jpg'; break;
				case 'Badger': backGroundImage = 'https://www.looper.com/img/gallery/youll-barely-recognize-badger-from-breaking-bad-now/l-intro-1615578631.jpg'; break;
				default: //nothing
			}
		})
		

</script>

<main>
	<div class="all-content">
		<div class="quote-class">
			<h1>"{quote}" </h1>
		</div>
		<h3>{author}</h3>
		<button class="breaking-bad-button" onclick="window.location.reload();">Next Quote</button>
	</div>
	<img alt="character" src={backGroundImage}>
	<p>Made by <a href="https://github.com/yassine128">Yassine Seddaoui</a></p>
</main>

<style>
	@import url('https://fonts.cdnfonts.com/css/heart-breaking-bad');

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	p {
		color: white;
		bottom: 1%;
		left: 1%;
		position: absolute;
	}

	.breaking-bad-button {
		background-color: #F9A11B; /* yellow color */
		color: black;
		font-family: 'Roboto', sans-serif;
		font-size: 18px;
		padding: 10px 20px;
		border-radius: 10px;
		border: none;
		cursor: pointer;
		text-align: center;
		text-transform: uppercase;
		letter-spacing: 2px;
		transition: all 0.2s ease-in-out;
		-webkit-animation: fadein 4s;
	}

	.breaking-bad-button:hover {
		background-color: #000000; /* black */
		color: white;
	}

	.all-content {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
	}


	h1 {
		font: bold italic 2em Georgia, Times, "Times New Roman", serif;
		font-size: 4em;
		font-weight: 100;
	}

	h3 {
		color: white;
		font-family: 'Heart Breaking Bad', sans-serif;
		font-size: 4em;
		-webkit-animation: fadein 4s;
	}

	.quote-class {
		color: white; 
		text-shadow:0 2px 0 #3B3B3B;
		-webkit-animation: fadein 4s;
	}

	/* Safari, Chrome and Opera > 12.1 */
	@-webkit-keyframes fadein {
		from { opacity: 0; }
		to   { opacity: 1; }
	}


	img {
		-webkit-animation: fadein 4s;
		filter: blur(8px);
		position: absolute;
		background-size: cover;
		height: 100%;
		width: 100%;
		top: 0;
		left: 0;
		z-index: -1;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>