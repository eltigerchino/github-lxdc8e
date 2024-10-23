<script>
	import Header from './Header.svelte';
	import './styles.css';
	import { onMount } from 'svelte';

	onMount(() => {
		addEventListener('popstate', (event) => {
			console.log(event)
		})
	})
</script>

<div class="app">
	<Header />

	<main>
		<a href="#footer">Go to footer</a>
		<slot />
	</main>

	<footer id="footer">
		<p>visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to learn SvelteKit</p>
	</footer>
</div>

<style>
	.app {
		height: 100%;
		overflow: auto;
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
