<script>
	import WrenchTitle from '../components/WrenchTitle/WrenchTitle.svelte';
</script>
<style>
	.WrenchTitle, h1, figure, p {
		text-align: center;
		margin: 0 auto;
	}
	.WrenchTitle{
		display: block;
		margin: auto;
		margin-bottom: 0.5em;
	}
	h1 {
		font-size: 2.8em;
		text-transform: uppercase;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}

	figure {
		margin: 0 0 1em 0;
	}

	img {
		width: 100%;
		max-width: 400px;
		margin: 0 0 1em 0;
	}

	p {
		margin: 1em auto;
	}

	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}
</style>

<svelte:head>
	<title>Sapper project template</title>
</svelte:head>

<WrenchTitle class="WrenchTitle" titleHat="titleHat" fontSize="2.8"  subTitle="subTitle">Great success!</WrenchTitle>


<figure>
	<img alt='Success Kid' src='successkid.jpg'>
	<figcaption>Have fun with Sapper!</figcaption>
</figure>

<p><strong>Try editing this file (src/routes/index.svelte) to test live reloading.</strong></p>
