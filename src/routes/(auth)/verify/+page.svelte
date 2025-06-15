<script>
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
	
	let countdown = 60;
	let canResend = false;
	
	// Countdown timer for resend button
	const startCountdown = () => {
		canResend = false;
		countdown = 60;
		const timer = setInterval(() => {
			countdown--;
			if (countdown <= 0) {
				clearInterval(timer);
				canResend = true;
			}
		}, 1000);
	};
	
	// Start countdown on component mount
	if (typeof window !== 'undefined') {
		startCountdown();
	}
</script>

<div class="flex min-h-screen items-center justify-center bg-slate-950 px-4 py-8">
	<div class="w-full max-w-md">
		<div class="relative overflow-hidden rounded-2xl bg-slate-900/80 backdrop-blur-sm border border-slate-800/50 shadow-2xl">
			<div class="absolute inset-0 bg-gradient-to-br from-cyan-500/5 via-transparent to-blue-500/5"></div>
			
			<div class="relative px-8 py-10">
				<!-- Header -->
				<div class="mb-8 text-center">
					<div class="mb-4">
						<div class="mx-auto h-12 w-12 rounded-full bg-gradient-to-r from-cyan-500 to-blue-600 flex items-center justify-center">
							<svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
							</svg>
						</div>
					</div>
					<h1 class="text-3xl font-bold text-white mb-2">Check your email</h1>
					<p class="text-slate-400 mb-4">We sent a verification code to</p>
					<p class="text-white font-medium">john.doe@example.com</p>
				</div>

				<form method="POST" class="space-y-6">
					<!-- Verification Code Input -->
					<div class="space-y-2">
						<label for="code" class="block text-sm font-medium text-slate-300">
							Verification code
						</label>
						<Input 
							id="code" 
							type="text" 
							placeholder="Enter 6-digit code"
							class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-cyan-500 focus:ring-cyan-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200 text-center text-lg font-mono tracking-widest"
							required
						/>
						<p class="text-xs text-slate-400">Enter the 6-digit code sent to your email</p>
					</div>

					<!-- Verify Button -->
					<Button 
						type="submit" 
						class="w-full h-12 bg-gradient-to-r from-cyan-600 to-blue-600 hover:from-cyan-700 hover:to-blue-700 text-white font-medium rounded-lg transition-all duration-200 shadow-lg hover:shadow-cyan-500/25"
					>
						Verify email
					</Button>
				</form>

				<!-- Resend Code -->
				<div class="mt-6 text-center">
					<p class="text-slate-400 mb-3">Didn't receive the code?</p>
					{#if canResend}
						<Button 
							type="button"
							onclick={() => startCountdown()}
							class="bg-transparent hover:bg-slate-800 text-cyan-400 hover:text-cyan-300 border border-slate-700 hover:border-slate-600 px-6 py-2 rounded-lg transition-all duration-200"
						>
							Resend code
						</Button>
					{:else}
						<Button 
							type="button"
							disabled
							class="bg-slate-800 text-slate-500 border border-slate-700 px-6 py-2 rounded-lg cursor-not-allowed"
						>
							Resend in {countdown}s
						</Button>
					{/if}
				</div>

				<!-- Change Email -->
				<div class="mt-6 text-center">
					<a href="/register" class="text-sm text-slate-400 hover:text-white transition-colors">
						Wrong email? Change it here
					</a>
				</div>
			</div>
		</div>

		<div class="mt-6 text-center">
			<p class="text-xs text-slate-500">
				💡 Check your spam folder if you don't see the email
			</p>
		</div>
	</div>
</div>
