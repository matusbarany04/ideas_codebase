<script>
	import Header from '../lib/components/Header.svelte';
	import Footer from '../lib/components/Footer.svelte';
	// import './styles.css';
</script>

<div class="app">
	<Header />

	<main>
		<slot />
	</main>

	<Footer />
	
</div>

<style >
	*{
		--primary-color: #09BC8A;
		--secondary-color: #A3320B;
		--tertiary-color: #48BEFF;
		--background-color: #010101;
		--text: white;	
		/* font-family: Arial, Helvetica, sans-serif; */
		font-family: monospace;

	
	}

	
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		overflow: hidden;
		background-color: var(--background-color);
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		width: 100%;
		margin: 0 auto;
		box-sizing: border-box;
		color: var(--text);
		max-width: 95vw;
		background-color: var(--background-color);
	
	}
</style>
