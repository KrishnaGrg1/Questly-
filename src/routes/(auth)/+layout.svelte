<script lang="ts">
	let { children } = $props();
</script>

<div>
	<main class="container">
		{@render children?.()}
	</main>
</div>
