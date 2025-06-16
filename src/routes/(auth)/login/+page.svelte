<script lang="ts">
    import { Button } from '$lib/components/ui/button';
    import { Input } from '$lib/components/ui/input';
</script>

<div class="flex min-h-screen mt-18 items-center justify-center bg-slate-950 px-4 py-8">
    <div class="w-full max-w-md">
        <!-- Login Card -->
        <div class="relative overflow-hidden rounded-2xl bg-slate-900/80 backdrop-blur-sm border border-slate-800/50 shadow-2xl">
            <!-- Gradient overlay for visual appeal -->
            <div class="absolute inset-0 bg-gradient-to-br from-blue-500/5 via-transparent to-indigo-500/5"></div>

            <div class="relative px-8 py-10">
                <!-- Header -->
                <div class="mb-8 text-center">
                    <div class="mb-4">
                        <div class="mx-auto h-12 w-12 rounded-full bg-gradient-to-r from-blue-500 to-indigo-600 flex items-center justify-center">
                            <svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                            </svg>
                        </div>
                    </div>
                    <h1 class="text-3xl font-bold text-white mb-2">Welcome back</h1>
                    <p class="text-slate-400">Sign in to continue your journey</p>
                </div>

                <!-- Form -->
                <form method="POST" class="space-y-6">
                    <!-- Email Field -->
                    <div class="space-y-2">
                        <label for="email" class="block text-sm font-medium text-slate-300">
                            Email address
                        </label>
                        <div class="relative">
                            <Input
                                id="email"
                                type="email"
                                placeholder="Enter your email"
                                class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-blue-500 focus:ring-blue-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
                                aria-label="Email address"
                            />
                        </div>
                    </div>

                    <!-- Password Field -->
                    <div class="space-y-2">
                        <label for="password" class="block text-sm font-medium text-slate-300">
                            Password
                        </label>
                        <div class="relative">
                            <Input
                                id="password"
                                type="password"
                                placeholder="Enter your password"
                                class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-blue-500 focus:ring-blue-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
                                aria-label="Password"
                            />
                        </div>
                    </div>

                    <!-- Remember me & Forgot password -->
                    <div class="flex items-center justify-between">
                        <label class="flex items-center space-x-2 cursor-pointer">
                            <input type="checkbox" class="h-4 w-4 rounded border-slate-600 bg-slate-800 text-blue-600 focus:ring-blue-500/20" />
                            <span class="text-sm text-slate-300">Remember me</span>
                        </label>
                        <a href="/forget-password" class="text-sm text-blue-400 hover:text-blue-300 transition-colors">
                            Forgot password?
                        </a>
                    </div>

                    <!-- Login Button -->
                    <Button
                        type="submit"
                        class="w-full h-12 bg-gradient-to-r from-blue-600 to-indigo-600 hover:from-blue-700 hover:to-indigo-700 text-white font-medium rounded-lg transition-all duration-200 shadow-lg hover:shadow-blue-500/25"
                    >
                        Sign in
                    </Button>

                    <!-- Divider -->
                    <div class="relative my-6">
                        <div class="absolute inset-0 flex items-center">
                            <div class="w-full border-t border-slate-700"></div>
                        </div>
                        <div class="relative flex justify-center text-sm">
                            <span class="bg-slate-900 px-4 text-slate-400">Or continue with</span>
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
                </form>

                <!-- Sign up link -->
                <div class="mt-8 text-center">
                    <p class="text-slate-400">
                        Don't have an account?
                        <a href="/register" class="ml-1 text-blue-400 hover:text-blue-300 font-medium transition-colors">
                            Create one now
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