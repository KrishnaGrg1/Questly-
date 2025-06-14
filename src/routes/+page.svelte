<script lang="ts">
	import Navbar from '$lib/components/Navbar.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import { Zap, Target, Sparkles, Brain, Users } from '@lucide/svelte';
</script>

<div class="bg-slate-950">
	<Navbar />

	<main class="mt-17 bg-slate-950 text-white">
		<!-- Hero Section -->
		<section class="py-24 text-center">
			<div class="mx-auto max-w-4xl px-4">
				<h1 class="mb-4 text-4xl font-bold text-indigo-400 sm:text-5xl">
					Level Up Your Life with Daily Quests
				</h1>
				<p class="mb-6 text-lg text-slate-400">
					Gamify your goals, track your habits, and visualize your future self.
				</p>
				<a
					href="/signup"
					class="inline-flex items-center gap-2 rounded-lg bg-indigo-600 px-6 py-3 font-semibold text-white transition-all duration-200 hover:scale-105 hover:bg-indigo-700"
				>
					<Zap class="h-5 w-5" /> Start Your Journey
				</a>
			</div>
		</section>

		<!-- Features Section -->
		<section class="bg-slate-900 py-24">
			<div class="mx-auto max-w-6xl px-6">
				<h2 class="mb-12 text-center text-3xl font-bold">Why Questly?</h2>
				<div class="grid gap-10 text-center md:grid-cols-3">
					<div>
						<Sparkles class="mx-auto mb-4 h-10 w-10 text-indigo-400" />
						<h3 class="mb-2 text-xl font-semibold">AI-Generated Daily Quests</h3>
						<p class="text-slate-400">
							Quests tailored to your goals by AI. Fresh, motivating, and personal.
						</p>
					</div>
					<div>
						<Target class="mx-auto mb-4 h-10 w-10 text-indigo-400" />
						<h3 class="mb-2 text-xl font-semibold">Goal-Driven Dashboard</h3>
						<p class="text-slate-400">
							Track habits, complete tasks, earn XP, and stay focused on your vision.
						</p>
					</div>
					<div>
						<Brain class="mx-auto mb-4 h-10 w-10 text-indigo-400" />
						<h3 class="mb-2 text-xl font-semibold">Visualize Your Future</h3>
						<p class="text-slate-400">
							AI simulates your dream life as you progress — level up in real life.
						</p>
					</div>
				</div>
			</div>
		</section>

		<!-- Stats Section -->
		<section class="bg-slate-950 py-24">
			<div class="mx-auto max-w-5xl px-6 text-center">
				<h2 class="mb-8 text-3xl font-bold">Join a Growing Movement</h2>
				<div class="grid grid-cols-1 gap-6 text-slate-300 sm:grid-cols-3">
					<div>
						<p class="text-4xl font-bold text-indigo-400">20k+</p>
						<p>Users leveling up</p>
					</div>
					<div>
						<p class="text-4xl font-bold text-indigo-400">1M+</p>
						<p>Quests completed</p>
					</div>
					<div>
						<p class="text-4xl font-bold text-indigo-400">98%</p>
						<p>Habit success rate</p>
					</div>
				</div>
			</div>
		</section>

		<!-- CTA Section (already had) -->
		<section class="bg-gray-900 py-24 text-white">
			<div class="mx-auto max-w-4xl px-4 text-center sm:px-6 lg:px-8">
				<h2 class="mb-6 text-3xl font-bold sm:text-4xl">Ready to Begin Your Quest?</h2>
				<p class="mb-8 text-xl text-gray-300">
					Join thousands of adventurers who have transformed their lives with Questly
				</p>
				<a
					href="/signup"
					class="inline-flex transform items-center rounded-xl bg-indigo-600 px-8 py-4 text-lg font-semibold text-white transition-all duration-200 hover:scale-105 hover:bg-indigo-700"
				>
					<Zap class="mr-2 h-6 w-6" />
					Start Free Today
				</a>
			</div>
		</section>
	</main>

	<Footer />
</div>
