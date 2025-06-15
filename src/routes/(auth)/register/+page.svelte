<!-- REGISTER COMPONENT -->
<script>
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
</script>

<div class="flex min-h-screen items-center justify-center bg-slate-950 px-4 py-8">
	<div class="w-full max-w-md">
		<div class="relative overflow-hidden rounded-2xl bg-slate-900/80 backdrop-blur-sm border border-slate-800/50 shadow-2xl">
			<div class="absolute inset-0 bg-gradient-to-br from-green-500/5 via-transparent to-blue-500/5"></div>
			
			<div class="relative px-8 py-10">
				<!-- Header -->
				<div class="mb-8 text-center">
					<div class="mb-4">
						<div class="mx-auto h-12 w-12 rounded-full bg-gradient-to-r from-green-500 to-blue-600 flex items-center justify-center">
							<svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18 9v3m0 0v3m0-3h3m-3 0h-3m-2-5a4 4 0 11-8 0 4 4 0 018 0zM3 20a6 6 0 0112 0v1H3v-1z" />
							</svg>
						</div>
					</div>
					<h1 class="text-3xl font-bold text-white mb-2">Create account</h1>
					<p class="text-slate-400">Start your journey with us today</p>
				</div>

				<form method="POST" class="space-y-6">
					<!-- Name Fields -->
					<div class="grid grid-cols-2 gap-4">
						<div class="space-y-2">
							<label for="firstName" class="block text-sm font-medium text-slate-300">
								First name
							</label>
							<Input 
								id="firstName" 
								type="text" 
								placeholder="John"
								class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-green-500 focus:ring-green-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
								required
							/>
						</div>
						<div class="space-y-2">
							<label for="lastName" class="block text-sm font-medium text-slate-300">
								Last name
							</label>
							<Input 
								id="lastName" 
								type="text" 
								placeholder="Doe"
								class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-green-500 focus:ring-green-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
								required
							/>
						</div>
					</div>

					<!-- Email Field -->
					<div class="space-y-2">
						<label for="email" class="block text-sm font-medium text-slate-300">
							Email address
						</label>
						<Input 
							id="email" 
							type="email" 
							placeholder="john.doe@example.com"
							class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-green-500 focus:ring-green-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
							required
						/>
					</div>

					<!-- Password Fields -->
					<div class="space-y-2">
						<label for="password" class="block text-sm font-medium text-slate-300">
							Password
						</label>
						<Input 
							id="password" 
							type="password" 
							placeholder="Create a strong password"
							class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-green-500 focus:ring-green-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
							required
						/>
						<p class="text-xs text-slate-400">Must be at least 8 characters with numbers and letters</p>
					</div>

					<div class="space-y-2">
						<label for="confirmPassword" class="block text-sm font-medium text-slate-300">
							Confirm password
						</label>
						<Input 
							id="confirmPassword" 
							type="password" 
							placeholder="Confirm your password"
							class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-green-500 focus:ring-green-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
							required
						/>
					</div>

					<!-- Terms & Privacy -->
					<div class="flex items-start space-x-2">
						<input type="checkbox" id="terms" class="mt-1 h-4 w-4 rounded border-slate-600 bg-slate-800 text-green-600 focus:ring-green-500/20" required>
						<label for="terms" class="text-sm text-slate-300">
							I agree to the 
							<a href="/terms" class="text-green-400 hover:text-green-300">Terms of Service</a> 
							and 
							<a href="/privacy" class="text-green-400 hover:text-green-300">Privacy Policy</a>
						</label>
					</div>

					<!-- Register Button -->
					<Button 
						type="submit" 
						class="w-full h-12 bg-gradient-to-r from-green-600 to-blue-600 hover:from-green-700 hover:to-blue-700 text-white font-medium rounded-lg transition-all duration-200 shadow-lg hover:shadow-green-500/25"
					>
						Create account
					</Button>

					<!-- Divider -->
					<div class="relative my-6">
						<div class="absolute inset-0 flex items-center">
							<div class="w-full border-t border-slate-700"></div>
						</div>
						<div class="relative flex justify-center text-sm">
							<span class="bg-slate-900 px-4 text-slate-400">Or sign up with</span>
						</div>
					</div>

					<!-- Social Register Options -->
					<div class="grid grid-cols-2 gap-3">
						<Button 
							type="button"
							class="h-11 bg-slate-800 hover:bg-slate-700 text-slate-300 border border-slate-700 rounded-lg transition-all duration-200"
						>
							<svg class="h-5 w-5 mr-2" viewBox="0 0 24 24" fill="currentColor">
								<path d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z" fill="#4285F4"/>
								<path d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z" fill="#34A853"/>
								<path d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l2.85-2.22.81-.62z" fill="#FBBC05"/>
								<path d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z" fill="#EA4335"/>
							</svg>
							Google
						</Button>
						<Button 
							type="button"
							class="h-11 bg-slate-800 hover:bg-slate-700 text-slate-300 border border-slate-700 rounded-lg transition-all duration-200"
						>
							<svg class="h-5 w-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
								<path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
							</svg>
							Facebook
						</Button>
					</div>
				</form>

				<!-- Sign in link -->
				<div class="mt-8 text-center">
					<p class="text-slate-400">
						Already have an account?
						<a href="/login" class="ml-1 text-green-400 hover:text-green-300 font-medium transition-colors">
							Sign in here
						</a>
					</p>
				</div>
			</div>
		</div>

		<div class="mt-6 text-center">
			<p class="text-xs text-slate-500">
				🔒 Your information is secure and encrypted
			</p>
		</div>
	</div>
</div>