<script lang="ts">
    import { Button } from '$lib/components/ui/button';
    import { Input } from '$lib/components/ui/input';

    // Form state
    let email = '';
    let password = '';
    let confirmPassword = '';
    let username = '';
</script>

<div class="flex min-h-screen mt-18 items-center justify-center bg-slate-950 px-4 py-8">
    <div class="w-full max-w-md">
        <!-- Register Card -->
        <div class="relative overflow-hidden rounded-2xl bg-slate-900/80 backdrop-blur-sm border border-slate-800/50 shadow-2xl">
            <!-- Gradient overlay -->
            <div class="absolute inset-0 bg-gradient-to-br from-purple-500/5 via-transparent to-blue-500/5"></div>
            
            <div class="relative px-8 py-10">
                <!-- Header -->
                <div class="mb-8 text-center">
                    <div class="mb-4 flex justify-center">
                        <div class="h-12 w-12 rounded-full bg-gradient-to-r from-purple-500 to-blue-600 flex items-center justify-center">
                            <svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                            </svg>
                        </div>
                    </div>
                    <h1 class="text-3xl font-bold text-white mb-2">Create Account</h1>
                    <p class="text-slate-400">Join Questly and start leveling up today</p>
                </div>

                <!-- Form -->
                <form method="POST" class="space-y-6">
                    <!-- Username Field -->
                    <div class="space-y-2">
                        <label for="username" class="block text-sm font-medium text-slate-300">
                            Username
                        </label>
                        <Input
                            id="username"
                            type="text"
                            bind:value={username}
                            placeholder="Choose a username"
                            class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-purple-500 focus:ring-purple-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
                            aria-label="Username"
                        />
                    </div>

                    <!-- Email Field -->
                    <div class="space-y-2">
                        <label for="email" class="block text-sm font-medium text-slate-300">
                            Email address
                        </label>
                        <Input
                            id="email"
                            type="email"
                            bind:value={email}
                            placeholder="Enter your email"
                            class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-purple-500 focus:ring-purple-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
                            aria-label="Email address"
                        />
                    </div>

                    <!-- Password Field -->
                    <div class="space-y-2">
                        <label for="password" class="block text-sm font-medium text-slate-300">
                            Password
                        </label>
                        <Input
                            id="password"
                            type="password"
                            bind:value={password}
                            placeholder="Create a password"
                            class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-purple-500 focus:ring-purple-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
                            aria-label="Password"
                        />
                    </div>

                    <!-- Confirm Password Field -->
                    <div class="space-y-2">
                        <label for="confirm-password" class="block text-sm font-medium text-slate-300">
                            Confirm Password
                        </label>
                        <Input
                            id="confirm-password"
                            type="password"
                            bind:value={confirmPassword}
                            placeholder="Re-enter your password"
                            class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-purple-500 focus:ring-purple-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
                            aria-label="Confirm Password"
                        />
                    </div>

                    <!-- Terms Checkbox -->
                    <label class="flex items-start space-x-2 cursor-pointer">
                        <input type="checkbox" class="mt-1 h-4 w-4 rounded border-slate-600 bg-slate-800 text-purple-600 focus:ring-purple-500/20" />
                        <span class="text-sm text-slate-300">
                            I agree to the <a href="/terms" class="text-purple-400 hover:text-purple-300">Terms of Service</a> and <a href="/privacy" class="text-purple-400 hover:text-purple-300">Privacy Policy</a>
                        </span>
                    </label>

                    <!-- Register Button -->
                    <Button
                        type="submit"
                        class="w-full h-12 bg-gradient-to-r from-purple-600 to-blue-600 hover:from-purple-700 hover:to-blue-700 text-white font-medium rounded-lg transition-all duration-200 shadow-lg hover:shadow-purple-500/25"
                    >
                        Create Account
                    </Button>
                </form>

                <!-- Divider -->
                <div class="relative my-6">
                    <div class="absolute inset-0 flex items-center">
                        <div class="w-full border-t border-slate-700"></div>
                    </div>
                    <div class="relative flex justify-center text-sm">
                        <span class="bg-slate-900 px-4 text-slate-400">Or sign up with</span>
                    </div>
                </div>

                <!-- Social Login Options -->
                <div class="grid grid-cols-2 gap-3">
                    <Button
                        type="button"
                        class="h-11 bg-slate-800 hover:bg-slate-700 text-slate-300 border border-slate-700 rounded-lg transition-all duration-200"
                        aria-label="Continue with Google"
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
                        aria-label="Continue with Facebook"
                    >
                        <svg class="h-5 w-5 mr-2" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                        </svg>
                        Facebook
                    </Button>
                </div>

                <!-- Login Link -->
                <div class="mt-8 text-center">
                    <p class="text-slate-400">
                        Already have an account?
                        <a href="/login" class="ml-1 text-purple-400 hover:text-purple-300 font-medium transition-colors">
                            Sign in
                        </a>
                    </p>
                </div>
            </div>
        </div>

        <!-- Trust indicators -->
        <div class="mt-6 text-center">
            <p class="text-xs text-slate-500">
                🔒 Your information is secure and encrypted
            </p>
        </div>
    </div>
</div>