<script>
	const posts = [
		{
			title: 'Introducing Questly 2.0',
			date: 'June 10, 2025',
			description: 'Explore all the new features and improvements in our biggest update yet.',
			link: '#'
		},
		{
			title: '5 Ways to Improve Team Feedback Loops',
			date: 'May 28, 2025',
			description: 'Learn how to gather and act on feedback more efficiently.',
			link: '#'
		}
	];
</script>

<section class="mx-auto mt-17 max-w-5xl px-8 py-16 text-white">
	<h1 class="mb-6 text-4xl font-bold">Blog</h1>
	<p class="mb-10 text-lg text-gray-300">Stay updated with our latest news and articles.</p>

	{#each posts as post}
		<article class="mb-8 rounded-lg bg-slate-800 p-6 shadow">
			<h2 class="text-2xl font-semibold">{post.title}</h2>
			<p class="mb-2 text-sm text-gray-400">{post.date}</p>
			<p class="mb-3">{post.description}</p>
			<a href={post.link} class="text-blue-400 hover:underline">Read more →</a>
		</article>
	{/each}
</section>
