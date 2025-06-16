<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import OtpInput from '$lib/components/ui/OtpInput/OtpInput.svelte';
	import { onMount } from 'svelte';

	let otpValue: string;
	let countdown = 60;
	let canResend = false;
	let email = 'john.doe@example.com'; // <- Dynamically bind this via prop or load function

	const handleComplete = (value: string) => {
		otpValue = value;
		console.log('OTP completed:', value);
	};

	const startCountdown = () => {
		canResend = false;
		countdown = 60;
		const timer = setInterval(() => {
			countdown--;
			if (countdown <= 0) {
				canResend = true;
				clearInterval(timer);
			}
		}, 1000);
	};

	onMount(() => {
		startCountdown();
	});
</script>

<div class="flex min-h-screen items-center justify-center bg-slate-950 px-4 py-8">
	<div class="w-full max-w-md">
		<!-- Card -->
		<div class="relative overflow-hidden rounded-2xl border border-slate-800/50 bg-slate-900/80 shadow-2xl backdrop-blur-sm">
			<!-- Light gradient -->
			<div class="absolute inset-0 bg-gradient-to-br from-cyan-500/5 via-transparent to-blue-500/5"></div>

			<!-- Content -->
			<div class="relative px-8 py-10 text-white">
				<!-- Header -->
				<div class="mb-8 text-center">
					<div class="mb-4 flex justify-center">
						<div class="h-12 w-12 flex items-center justify-center rounded-full bg-gradient-to-r from-cyan-500 to-blue-600">
							<svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
							</svg>
						</div>
					</div>
					<h1 class="text-3xl font-bold mb-2">Check your email</h1>
					<p class="text-slate-400">We sent a 6-digit verification code to:</p>
					<p class="font-medium text-white mt-1">{email}</p>
				</div>

				<form method="POST" class="space-y-6">
					<!-- OTP Input -->
					 <OtpInput length={6} on:complete={(e) => console.log('OTP is:', e.detail)} />
					<p class="text-xs text-slate-400 text-center">Enter the 6-digit code sent to your email</p>

					<!-- Submit Button -->
					<Button type="submit" class="h-12 w-full rounded-lg bg-gradient-to-r from-cyan-600 to-blue-600 font-medium text-white shadow-lg transition-all duration-200 hover:from-cyan-700 hover:to-blue-700 hover:shadow-cyan-500/25">
						Verify Email
					</Button>
				</form>

				<!-- Resend & Change -->
				<div class="mt-6 text-center">
					{#if canResend}
						<Button onclick={startCountdown} type="button" class="mt-2 rounded-lg border border-slate-700 bg-transparent px-6 py-2 text-cyan-400 transition-all duration-200 hover:border-slate-600 hover:bg-slate-800 hover:text-cyan-300">
							Resend Code
						</Button>
					{:else}
						<Button disabled type="button" class="mt-2 cursor-not-allowed rounded-lg border border-slate-700 bg-slate-800 px-6 py-2 text-slate-500">
							Resend in {countdown}s
						</Button>
					{/if}

					<div class="mt-4">
						<a href="/login" class="text-sm text-slate-400 hover:text-white">Wrong email? Change it here</a>
					</div>
				</div>
			</div>
		</div>

		<!-- Helper Note -->
		<div class="mt-6 text-center">
			<p class="text-xs text-slate-500">💡 Check your spam folder if you don’t see the email.</p>
		</div>
	</div>
</div>
