<script lang="ts">
    import { Button } from '$lib/components/ui/button';
    import { Input } from '$lib/components/ui/input';
    let email = '';
</script>

<div class="flex min-h-screen mt-18 items-center justify-center bg-slate-950 px-4 py-8">
    <div class="w-full max-w-md">
        <div class="relative overflow-hidden rounded-2xl bg-slate-900/80 backdrop-blur-sm border border-slate-800/50 shadow-2xl">
            <div class="absolute inset-0 bg-gradient-to-br from-purple-500/5 via-transparent to-blue-500/5"></div>
            <div class="relative px-8 py-10">
                <div class="mb-8 text-center">
                    <div class="mb-4 flex justify-center">
                        <div class="h-12 w-12 rounded-full bg-gradient-to-r from-purple-500 to-blue-600 flex items-center justify-center">
                            <svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2z" />
                            </svg>
                        </div>
                    </div>
                    <h1 class="text-3xl font-bold text-white mb-2">Forgot Password?</h1>
                    <p class="text-slate-400">Enter your email and we'll send you instructions to reset it.</p>
                </div>

                <form method="POST" class="space-y-6">
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

                    <Button
                        type="submit"
                        class="w-full h-12 bg-gradient-to-r from-purple-600 to-blue-600 hover:from-purple-700 hover:to-blue-700 text-white font-medium rounded-lg transition-all duration-200 shadow-lg hover:shadow-purple-500/25"
                    >
                        Send Reset Link
                    </Button>
                </form>

                <div class="mt-8 text-center">
                    <a href="/login" class="text-sm text-purple-400 hover:text-purple-300 font-medium transition-colors">
                        ← Back to Sign In
                    </a>
                </div>
            </div>
        </div>
    </div>
</div>