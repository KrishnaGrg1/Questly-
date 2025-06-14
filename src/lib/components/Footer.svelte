<script>
	const year = new Date().getFullYear();
	import Logo from '$lib/components/Logo.svelte';
</script>

<footer class="border-t border-slate-800 bg-slate-950 text-slate-300">
	<div class="mx-auto grid max-w-7xl grid-cols-1 gap-8 p-8 md:grid-cols-4">
		<!-- Logo & Mission -->
		<div>
			<Logo />
			<p class="mt-3 text-sm text-slate-400">
				Level up your real life with daily quests, XP, and your AI-powered future.
			</p>
		</div>

		<!-- Explore -->
		<div>
			<h3 class="mb-2 text-sm font-semibold text-slate-400 uppercase">Explore</h3>
			<ul class="space-y-1 text-sm">
				<li><a href="/features" class="hover:text-indigo-400">Features</a></li>
				<li><a href="/how-it-works" class="hover:text-indigo-400">How It Works</a></li>
				<li><a href="/faq" class="hover:text-indigo-400">FAQ</a></li>
			</ul>
		</div>

		<!-- Account -->
		<div>
			<h3 class="mb-2 text-sm font-semibold text-slate-400 uppercase">Get Started</h3>
			<ul class="space-y-1 text-sm">
				<li><a href="/login" class="hover:text-indigo-400">Login</a></li>
				<li><a href="/signup" class="hover:text-indigo-400">Sign Up</a></li>
			</ul>
		</div>

		<!-- Company -->
		<div>
			<h3 class="mb-2 text-sm font-semibold text-slate-400 uppercase">Company</h3>
			<ul class="space-y-1 text-sm">
				<li><a href="/about" class="hover:text-indigo-400">About</a></li>
				<li><a href="/terms" class="hover:text-indigo-400">Terms of Service</a></li>
				<li><a href="/privacy" class="hover:text-indigo-400">Privacy Policy</a></li>
			</ul>
		</div>
	</div>

	<!-- Social + Bottom Strip -->
	<div class="mt-12 border-t border-slate-800 p-8 pt-6 text-center">
		<div class="mb-4 flex justify-center space-x-4">
			<a href="#" class="hover:text-indigo-400" aria-label="Twitter">🐦</a>
			<a href="#" class="hover:text-indigo-400" aria-label="Discord">💬</a>
			<a href="#" class="hover:text-indigo-400" aria-label="GitHub">💻</a>
		</div>
		<p class="text-sm text-slate-500">© {year} Questly. Forge your future, one quest at a time.</p>
	</div>
</footer>
