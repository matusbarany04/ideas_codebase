<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>
<script>
	import Card from "../../lib/components/Card.svelte";
	import { onMount } from "svelte";
	let posts = []
	

	onMount(async function () {
    	const response = await fetch("http://dismounted.tech:8000/api/ideas");
    	const data = await response.json();
    	console.log(data);
		posts = data;
	});

</script>
<h1>posts</h1>
<div class="text-column">
	<div class="cards">

		{#each posts as article}
			<Card data={article}></Card>
		
		{/each}
	</div>
  
</div>

<style>
	.cards{

		display: grid;
		align-items: center;
		grid-template-columns: repeat(4, 1fr);
		grid-gap: 1rem;
		row-gap: 2rem;
		justify-items: center;

	}

	@media(max-width: 100rem){
		.cards{
			grid-template-columns: repeat(3, 1fr) ;
		}
	}
	@media(max-width: 70rem){
		.cards{
			grid-template-columns: repeat(2, 1fr) ;
		}
	}

	@media(max-width: 50rem){
		.cards{
			grid-template-columns: 1fr;
		}
	}

	h1{
		text-align: center;
		font-size: 3rem;
	}
</style>
