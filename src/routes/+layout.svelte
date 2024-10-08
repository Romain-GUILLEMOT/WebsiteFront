<script>
	import Header from '../components/Header.svelte';
	import '../app.css';
	import { page } from '$app/stores';
	import Footer from '../Footer.svelte';

	let showHeader = false;

	$: {
		showHeader = $page.url.pathname !== '/';
	}
</script>


<div class="app">
	{#if showHeader}
	<Header />
	{/if}
	<main>
		<slot />
	</main>

<Footer/>
</div>

