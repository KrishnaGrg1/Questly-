<script lang="ts">
    import Navbar from '$lib/components/Navbar.svelte';
    import Footer from '$lib/components/Footer.svelte';
    import { Zap, Target, Sparkles, Brain, Users, Star, Trophy, Rocket, Shield, CheckCircle, ArrowRight, Play } from '@lucide/svelte';

    let heroRef;
    let featuresRef;
    let statsRef:any;

    // Animated counter for stats
    let userCount = 0;
    let questCount = 0;
    let successRate = 0;

    const animateStats = () => {
        const duration = 2000;
        const steps = 60;
        const userTarget = 20000;
        const questTarget = 1000000;
        const successTarget = 98;
        let step = 0;

        const interval = setInterval(() => {
            step++;
            const progress = step / steps;
            const easeOut = 1 - Math.pow(1 - progress, 3);
            userCount = Math.floor(userTarget * easeOut);
            questCount = Math.floor(questTarget * easeOut);
            successRate = Math.floor(successTarget * easeOut);

            if (step >= steps) {
                clearInterval(interval);
            }
        }, duration / steps);
    };

    // Particle animation
    let particles = [];
    if (typeof window !== 'undefined') {
        for (let i = 0; i < 50; i++) {
            particles.push({
                x: Math.random() * 100,
                y: Math.random() * 100,
                size: Math.random() * 4 + 1,
                speed: Math.random() * 2 + 0.5,
                opacity: Math.random() * 0.5 + 0.2
            });
        }
    }

    // Intersection Observer for animations
    if (typeof window !== 'undefined') {
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    if (entry.target === statsRef) {
                        animateStats();
                    }
                }
            });
        });

        setTimeout(() => {
            if (statsRef) observer.observe(statsRef);
        }, 100);
    }
</script>

<div class="bg-slate-950 overflow-hidden">
    <Navbar />
    <main class="mt-16 bg-slate-950 text-white relative">
        <!-- Animated Background -->
        <div class="fixed inset-0 overflow-hidden pointer-events-none">
            <div class="absolute inset-0 bg-gradient-to-br from-indigo-900/20 via-purple-900/10 to-pink-900/20"></div>
            {#each particles as particle}
                <div 
                    class="absolute w-1 h-1 bg-indigo-400 rounded-full animate-pulse"
                    style="left: {particle.x}%; top: {particle.y}%; opacity: {particle.opacity};"
                ></div>
            {/each}
        </div>

        <!-- Hero Section -->
        <section bind:this={heroRef} class="relative py-32 text-center overflow-hidden">
            <!-- Hero Background Effects -->
            <div class="absolute inset-0 bg-gradient-radial from-indigo-500/10 via-transparent to-transparent"></div>
            <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-gradient-to-r from-indigo-500/20 to-purple-500/20 rounded-full blur-3xl animate-pulse"></div>
            <div class="relative mx-auto max-w-6xl px-4 z-10">
                <!-- Badge -->
                <div class="inline-flex items-center gap-2 px-4 py-2 bg-indigo-500/10 border border-indigo-500/20 rounded-full text-indigo-300 text-sm font-medium mb-8">
                    <Sparkles class="h-4 w-4" />
                    Life Gamification Platform
                </div>
                <h1 class="mb-8 text-5xl md:text-7xl font-bold bg-gradient-to-r from-indigo-400 via-purple-400 to-pink-400 bg-clip-text text-transparent leading-tight">
                    Level Up Your Life<br/>
                    <span class="text-4xl md:text-6xl">with Daily Quests</span>
                </h1>
                <p class="mb-12 text-xl md:text-2xl text-slate-300 max-w-3xl mx-auto leading-relaxed">
                    Transform your goals into an epic adventure. Get AI-powered daily quests, 
                    track your progress, and visualize your dream future.
                </p>
                <!-- CTA Buttons -->
                <div class="flex flex-col sm:flex-row gap-4 justify-center items-center mb-16">
                    <a
                        href="/register"
                        class="group relative inline-flex items-center gap-3 px-8 py-4 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-2xl font-bold text-lg text-white transition-all duration-300 hover:scale-105 hover:shadow-2xl hover:shadow-indigo-500/25"
                    >
                        <Zap class="h-6 w-6 group-hover:animate-bounce" />
                        Start Your Epic Journey
                        <div class="absolute inset-0 bg-gradient-to-r from-indigo-500 to-purple-500 rounded-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-300 -z-10 blur"></div>
                    </a>
                    <button class="group inline-flex items-center gap-3 px-8 py-4 border-2 border-slate-600 rounded-2xl font-semibold text-lg text-slate-300 hover:border-indigo-400 hover:text-white transition-all duration-300">
                        <Play class="h-5 w-5 group-hover:scale-110 transition-transform" />
                        Watch Demo
                    </button>
                </div>
                <!-- Trust Indicators -->
                <div class="flex flex-wrap justify-center items-center gap-8 text-slate-400">
                    <div class="flex items-center gap-2">
                        <div class="flex">
                            {#each Array(5) as _}
                                <Star class="h-4 w-4 fill-yellow-400 text-yellow-400" />
                            {/each}
                        </div>
                        <span class="text-sm">4.9/5 Rating</span>
                    </div>
                    <div class="flex items-center gap-2">
                        <Shield class="h-4 w-4 text-green-400" />
                        <span class="text-sm">100% Secure</span>
                    </div>
                    <div class="flex items-center gap-2">
                        <Users class="h-4 w-4 text-blue-400" />
                        <span class="text-sm">20k+ Active Users</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Features Section -->
        <section bind:this={featuresRef} class="relative py-32 bg-gradient-to-b from-slate-950 to-slate-900">
            <div class="absolute inset-0 bg-grid-pattern opacity-5"></div>
            <div class="relative mx-auto max-w-7xl px-6 z-10">
                <div class="text-center mb-20">
                    <h2 class="text-4xl md:text-5xl font-bold mb-6 bg-gradient-to-r from-indigo-400 to-purple-400 bg-clip-text text-transparent">
                        Why Choose Questly?
                    </h2>
                    <p class="text-xl text-slate-400 max-w-2xl mx-auto">
                        Discover the features that make Questly the ultimate life gamification platform
                    </p>
                </div>
                <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
                    <!-- Feature 1 -->
                    <div class="group relative p-8 bg-gradient-to-br from-slate-800/50 to-slate-900/50 rounded-3xl border border-slate-700/50 hover:border-indigo-500/50 transition-all duration-500 hover:scale-105 hover:shadow-2xl hover:shadow-indigo-500/10">
                        <div class="absolute inset-0 bg-gradient-to-br from-indigo-500/5 to-purple-500/5 rounded-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                        <div class="relative">
                            <div class="w-16 h-16 bg-gradient-to-br from-indigo-500 to-purple-600 rounded-2xl flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                                <Sparkles class="h-8 w-8 text-white" />
                            </div>
                            <h3 class="text-2xl font-bold mb-4 text-white">AI-Powered Daily Quests</h3>
                            <p class="text-slate-400 leading-relaxed mb-6">
                                Get personalized daily challenges tailored to your goals. Our AI creates fresh, 
                                motivating quests that adapt to your progress.
                            </p>
                            <div class="flex items-center text-indigo-400 group-hover:text-indigo-300 transition-colors">
                                <span class="text-sm font-medium">Learn more</span>
                                <ArrowRight class="h-4 w-4 ml-2 group-hover:translate-x-1 transition-transform" />
                            </div>
                        </div>
                    </div>
                    <!-- Add other feature cards here -->
                </div>
            </div>
        </section>

        <!-- Stats Section -->
        <section bind:this={statsRef} class="relative py-32 bg-gradient-to-b from-slate-900 to-slate-950">
            <div class="absolute inset-0 bg-gradient-radial from-indigo-500/5 via-transparent to-transparent"></div>
            <div class="relative mx-auto max-w-6xl px-6 text-center z-10">
                <div class="mb-16">
                    <h2 class="text-4xl md:text-5xl font-bold mb-6 bg-gradient-to-r from-indigo-400 to-purple-400 bg-clip-text text-transparent">
                        Join the Life-Leveling Revolution
                    </h2>
                    <p class="text-xl text-slate-400 max-w-2xl mx-auto">
                        Thousands of adventurers are already transforming their lives with Questly
                    </p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-12">
                    <div class="group relative p-8 bg-gradient-to-br from-slate-800/30 to-slate-900/30 rounded-3xl border border-slate-700/30 hover:border-indigo-500/50 transition-all duration-500">
                        <div class="absolute inset-0 bg-gradient-to-br from-indigo-500/5 to-purple-500/5 rounded-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                        <div class="relative">
                            <div class="text-5xl md:text-6xl font-bold bg-gradient-to-r from-indigo-400 to-purple-400 bg-clip-text text-transparent mb-4">
                                {userCount.toLocaleString()}+
                            </div>
                            <p class="text-slate-300 text-lg font-medium mb-2">Active Adventurers</p>
                            <p class="text-slate-500 text-sm">Leveling up their lives daily</p>
                        </div>
                    </div>
                    <div class="group relative p-8 bg-gradient-to-br from-slate-800/30 to-slate-900/30 rounded-3xl border border-slate-700/30 hover:border-purple-500/50 transition-all duration-500">
                        <div class="absolute inset-0 bg-gradient-to-br from-purple-500/5 to-pink-500/5 rounded-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                        <div class="relative">
                            <div class="text-5xl md:text-6xl font-bold bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent mb-4">
                                {(questCount / 1000000).toFixed(1)}M+
                            </div>
                            <p class="text-slate-300 text-lg font-medium mb-2">Quests Completed</p>
                            <p class="text-slate-500 text-sm">Goals achieved and dreams realized</p>
                        </div>
                    </div>
                    <div class="group relative p-8 bg-gradient-to-br from-slate-800/30 to-slate-900/30 rounded-3xl border border-slate-700/30 hover:border-green-500/50 transition-all duration-500">
                        <div class="absolute inset-0 bg-gradient-to-br from-green-500/5 to-emerald-500/5 rounded-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                        <div class="relative">
                            <div class="text-5xl md:text-6xl font-bold bg-gradient-to-r from-green-400 to-emerald-400 bg-clip-text text-transparent mb-4">
                                {successRate}%
                            </div>
                            <p class="text-slate-300 text-lg font-medium mb-2">Success Rate</p>
                            <p class="text-slate-500 text-sm">Users who stick to their habits</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Testimonials Section -->
        <section class="relative py-32 bg-gradient-to-b from-slate-950 to-slate-900">
            <div class="relative mx-auto max-w-6xl px-6 z-10">
                <div class="text-center mb-20">
                    <h2 class="text-4xl md:text-5xl font-bold mb-6 bg-gradient-to-r from-indigo-400 to-purple-400 bg-clip-text text-transparent">
                        Life-Changing Stories
                    </h2>
                    <p class="text-xl text-slate-400 max-w-2xl mx-auto">
                        Real users, real transformations, real results
                    </p>
                </div>
                <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
                    <!-- Testimonial 1 -->
                    <div class="group relative p-8 bg-gradient-to-br from-slate-800/50 to-slate-900/50 rounded-3xl border border-slate-700/50 hover:border-indigo-500/50 transition-all duration-500">
                        <div class="absolute inset-0 bg-gradient-to-br from-indigo-500/5 to-purple-500/5 rounded-3xl opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                        <div class="relative">
                            <div class="flex mb-4">
                                {#each Array(5) as _}
                                    <Star class="h-5 w-5 fill-yellow-400 text-yellow-400" />
                                {/each}
                            </div>
                            <p class="text-slate-300 mb-6 leading-relaxed">
                                "Questly completely transformed how I approach my goals..."
                            </p>
                            <div class="flex items-center">
                                <div class="w-12 h-12 bg-gradient-to-br from-indigo-500 to-purple-600 rounded-full flex items-center justify-center mr-4">
                                    <span class="text-white font-bold">SM</span>
                                </div>
                                <div>
                                    <p class="text-white font-semibold">Sarah Mitchell</p>
                                    <p class="text-slate-400 text-sm">Entrepreneur</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Final CTA Section -->
        <section class="relative py-32 bg-gradient-to-br from-indigo-900/30 via-purple-900/20 to-pink-900/30">
            <div class="absolute inset-0 bg-gradient-radial from-indigo-500/10 via-transparent to-transparent"></div>
            <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-gradient-to-r from-indigo-500/20 to-purple-500/20 rounded-full blur-3xl"></div>
            <div class="relative mx-auto max-w-4xl px-4 text-center z-10">
                <div class="inline-flex items-center gap-2 px-4 py-2 bg-indigo-500/10 border border-indigo-500/20 rounded-full text-indigo-300 text-sm font-medium mb-8">
                    <Trophy class="h-4 w-4" />
                    Ready to Start Your Adventure?
                </div>
                <h2 class="mb-8 text-4xl md:text-6xl font-bold bg-gradient-to-r from-indigo-400 via-purple-400 to-pink-400 bg-clip-text text-transparent leading-tight">
                    Begin Your Epic Quest Today
                </h2>
                <p class="mb-12 text-xl md:text-2xl text-slate-300 max-w-2xl mx-auto leading-relaxed">
                    Join thousands of adventurers who have transformed their lives. Your future self is waiting.
                </p>
                <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mb-12">
                    <a
                        href="/register"
                        class="group relative inline-flex items-center gap-3 px-10 py-5 bg-gradient-to-r from-indigo-600 to-purple-600 rounded-2xl font-bold text-xl text-white transition-all duration-300 hover:scale-105 hover:shadow-2xl hover:shadow-indigo-500/25"
                    >
                        <Zap class="h-7 w-7 group-hover:animate-bounce" />
                        Start Free Forever
                        <div class="absolute inset-0 bg-gradient-to-r from-indigo-500 to-purple-500 rounded-2xl opacity-0 group-hover:opacity-100 transition-opacity duration-300 -z-10 blur"></div>
                    </a>
                </div>
            </div>
        </section>
    </main>

    <Footer />
</div>