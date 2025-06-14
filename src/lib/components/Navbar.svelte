<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import Logo from '$lib/components/Logo.svelte';
	import { goto } from '$app/navigation';
</script>

<nav
	class="fixed top-0 left-0 z-50 flex w-full flex-row items-center justify-between border-b border-slate-800 bg-slate-950 px-6 py-4 shadow-md"
>
	<div class="text-xl font-bold sm:text-2xl md:text-3xl">
		<Logo />
	</div>

	<div class="flex space-x-6 text-base text-gray-500 md:text-lg">
		<a href="/features" class="hover:text-gray-600">Features</a>
		<a href="/how-it-works" class="hover:text-gray-600">How It Works</a>
		<a href="/testimonials" class="hover:text-gray-600">Testimonials</a>
		<a href="/blog" class="hover:text-gray-600">Blog</a>
	</div>

	<div class="flex space-x-4">
		<Button
			onclick={() => goto('/login')}
			class="bg-transparent text-sm hover:bg-transparent hover:text-gray-300 md:text-base"
		>
			Log In
		</Button>
		<Button
			onclick={() => goto('/register')}
			class="rounded bg-blue-600 px-4 py-2 text-sm text-white hover:bg-blue-700 md:text-base"
		>
			Get Started
		</Button>
	</div>
</nav>
