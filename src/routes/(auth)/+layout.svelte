<script lang="ts">
	import Navbar from '$lib/components/Navbar.svelte';
	let { children } = $props();
	import Footer from '$lib/components/Footer.svelte';
</script>

<div class="bg-slate-950">
	<Navbar />
	<main class="container">
		{@render children?.()}
	</main>
	<Footer />
</div>
