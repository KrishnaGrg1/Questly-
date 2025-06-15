<!-- RESET PASSWORD COMPONENT -->
<script>
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
</script>

<div class="flex min-h-screen items-center justify-center bg-slate-950 px-4 py-8">
	<div class="w-full max-w-md">
		<div class="relative overflow-hidden rounded-2xl bg-slate-900/80 backdrop-blur-sm border border-slate-800/50 shadow-2xl">
			<div class="absolute inset-0 bg-gradient-to-br from-purple-500/5 via-transparent to-pink-500/5"></div>
			
			<div class="relative px-8 py-10">
				<!-- Header -->
				<div class="mb-8 text-center">
					<div class="mb-4">
						<div class="mx-auto h-12 w-12 rounded-full bg-gradient-to-r from-purple-500 to-pink-600 flex items-center justify-center">
							<svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
							</svg>
						</div>
					</div>
					<h1 class="text-3xl font-bold text-white mb-2">Reset password</h1>
					<p class="text-slate-400">Enter your new password below</p>
				</div>

				<form method="POST" class="space-y-6">
					<!-- New Password Field -->
					<div class="space-y-2">
						<label for="password" class="block text-sm font-medium text-slate-300">
							New password
						</label>
						<Input 
							id="password" 
							type="password" 
							placeholder="Create a strong password"
							class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-purple-500 focus:ring-purple-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
							required
						/>
						<p class="text-xs text-slate-400">Must be at least 8 characters with numbers and letters</p>
					</div>

					<!-- Confirm Password Field -->
					<div class="space-y-2">
						<label for="confirmPassword" class="block text-sm font-medium text-slate-300">
							Confirm new password
						</label>
						<Input 
							id="confirmPassword" 
							type="password" 
							placeholder="Confirm your new password"
							class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-purple-500 focus:ring-purple-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
							required
						/>
					</div>

					<!-- Password Requirements -->
					<div class="bg-slate-800/30 border border-slate-700 rounded-lg p-4">
						<h4 class="text-sm font-medium text-slate-300 mb-2">Password requirements:</h4>
						<ul class="text-xs text-slate-400 space-y-1">
							<li class="flex items-center">
								<span class="w-1 h-1 bg-slate-500 rounded-full mr-2"></span>
								At least 8 characters long
							</li>
							<li class="flex items-center">
								<span class="w-1 h-1 bg-slate-500 rounded-full mr-2"></span>
								Contains uppercase and lowercase letters
							</li>
							<li class="flex items-center">
								<span class="w-1 h-1 bg-slate-500 rounded-full mr-2"></span>
								Contains at least one number
							</li>
							<li class="flex items-center">
								<span class="w-1 h-1 bg-slate-500 rounded-full mr-2"></span>
								Contains at least one special character
							</li>
						</ul>
					</div>

					<!-- Reset Button -->
					<Button 
						type="submit" 
						class="w-full h-12 bg-gradient-to-r from-purple-600 to-pink-600 hover:from-purple-700 hover:to-pink-700 text-white font-medium rounded-lg transition-all duration-200 shadow-lg hover:shadow-purple-500/25"
					>
						Update password
					</Button>
				</form>

				<!-- Back to login -->
				<div class="mt-8 text-center">
					<a href="/login" class="inline-flex items-center text-slate-400 hover:text-white transition-colors">
						<svg class="h-4 w-4 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
							<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
						</svg>
						Back to login
					</a>
				</div>
			</div>
		</div>

		<div class="mt-6 text-center">
			<p class="text-xs text-slate-500">
				🔒 Your new password will be encrypted and secure
			</p>
		</div>
	</div>
</div>
