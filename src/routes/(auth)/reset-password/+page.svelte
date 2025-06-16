<script lang="ts">
    import { Button } from '$lib/components/ui/button';
    import { Input } from '$lib/components/ui/input';

    let newPassword = '';
    let confirmPassword = '';
    let token = '';
</script>

<div class="flex min-h-screen mt-18 items-center justify-center bg-slate-950 px-4 py-8">
    <div class="w-full max-w-md">
        <div class="relative overflow-hidden rounded-2xl bg-slate-900/80 backdrop-blur-sm border border-slate-800/50 shadow-2xl">
            <div class="absolute inset-0 bg-gradient-to-br from-blue-500/5 via-transparent to-indigo-500/5"></div>
            <div class="relative px-8 py-10">
                <div class="mb-8 text-center">
                    <div class="mb-4 flex justify-center">
                        <div class="h-12 w-12 rounded-full bg-gradient-to-r from-blue-500 to-indigo-600 flex items-center justify-center">
                            <svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 7a2 2 0 11-4 0 2 2 0 014 0zm4 10a9 9 0 11-18 0 9 9 0 0118 0z" />
                            </svg>
                        </div>
                    </div>
                    <h1 class="text-3xl font-bold text-white mb-2">Reset Password</h1>
                    <p class="text-slate-400">Choose a new password below.</p>
                </div>

                <form method="POST" class="space-y-6">
                    <!-- Token -->
                    <Input type="hidden" bind:value={token} />

                    <!-- New Password -->
                    <div class="space-y-2">
                        <label for="newPassword" class="block text-sm font-medium text-slate-300">
                            New Password
                        </label>
                        <Input
                            id="newPassword"
                            type="password"
                            bind:value={newPassword}
                            placeholder="Enter new password"
                            class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-blue-500 focus:ring-blue-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
                            aria-label="New Password"
                        />
                    </div>

                    <!-- Confirm Password -->
                    <div class="space-y-2">
                        <label for="confirmPassword" class="block text-sm font-medium text-slate-300">
                            Confirm Password
                        </label>
                        <Input
                            id="confirmPassword"
                            type="password"
                            bind:value={confirmPassword}
                            placeholder="Re-enter password"
                            class="w-full bg-slate-800/50 border-slate-700 text-white placeholder:text-slate-400 focus:border-blue-500 focus:ring-blue-500/20 h-12 pl-4 pr-4 rounded-lg transition-all duration-200"
                            aria-label="Confirm Password"
                        />
                    </div>

                    <Button
                        type="submit"
                        class="w-full h-12 bg-gradient-to-r from-blue-600 to-indigo-600 hover:from-blue-700 hover:to-indigo-700 text-white font-medium rounded-lg transition-all duration-200 shadow-lg hover:shadow-blue-500/25"
                    >
                        Reset Password
                    </Button>
                </form>

                <div class="mt-8 text-center">
                    <a href="/login" class="text-sm text-blue-400 hover:text-blue-300 font-medium transition-colors">
                        ← Back to Login
                    </a>
                </div>
            </div>
        </div>
    </div>
</div>