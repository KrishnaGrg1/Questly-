<!-- FORGOT PASSWORD COMPONENT -->
<script>
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
</script>

<div class="flex min-h-screen items-center justify-center bg-slate-950 px-4 py-8">
	<div class="w-full max-w-md">
		<div
			class="relative overflow-hidden rounded-2xl border border-slate-800/50 bg-slate-900/80 shadow-2xl backdrop-blur-sm"
		>
			<div
				class="absolute inset-0 bg-gradient-to-br from-orange-500/5 via-transparent to-red-500/5"
			></div>

			<div class="relative px-8 py-10">
				<!-- Header -->
				<div class="mb-8 text-center">
					<div class="mb-4">
						<div
							class="mx-auto flex h-12 w-12 items-center justify-center rounded-full bg-gradient-to-r from-orange-500 to-red-600"
						>
							<svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M15 7a2 2 0 012 2m0 0a2 2 0 012 2m-2-2a2 2 0 00-2 2m2-2V5a2 2 0 00-2-2H9a2 2 0 00-2 2v14a2 2 0 002 2h2"
								/>
							</svg>
						</div>
					</div>
					<h1 class="mb-2 text-3xl font-bold text-white">Forgot password?</h1>
					<p class="text-slate-400">No worries, we'll send you reset instructions</p>
				</div>

				<form method="POST" class="space-y-6">
					<!-- Email Field -->
					<div class="space-y-2">
						<label for="email" class="block text-sm font-medium text-slate-300">
							Email address
						</label>
						<Input
							id="email"
							type="email"
							placeholder="Enter your email address"
							class="h-12 w-full rounded-lg border-slate-700 bg-slate-800/50 pr-4 pl-4 text-white transition-all duration-200 placeholder:text-slate-400 focus:border-orange-500 focus:ring-orange-500/20"
							required
						/>
						<p class="text-xs text-slate-400">
							We'll send password reset instructions to this email
						</p>
					</div>

					<!-- Reset Button -->
					<Button
						type="submit"
						class="h-12 w-full rounded-lg bg-gradient-to-r from-orange-600 to-red-600 font-medium text-white shadow-lg transition-all duration-200 hover:from-orange-700 hover:to-red-700 hover:shadow-orange-500/25"
					>
						Send reset Code
					</Button>
				</form>

				<!-- Back to login -->
				<div class="mt-8 text-center text-slate-400">
					Remember your password?
					<a
						href="/login"
						class="inline-flex items-center text-slate-400 transition-colors hover:text-white"
					>
						Log in
					</a>
				</div>
			</div>
		</div>

		<div class="mt-6 text-center">
			<p class="text-xs text-slate-500">💡 Check your spam folder if you don't see the email</p>
		</div>
	</div>
</div>
