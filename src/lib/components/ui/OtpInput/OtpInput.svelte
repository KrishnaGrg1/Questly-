<script lang="ts">
	import { createEventDispatcher, onMount } from 'svelte';
	export let length = 6;

	const dispatch = createEventDispatcher();
	let values: string[] = Array(length).fill('');
	let inputs: HTMLInputElement[] = [];

	// Move focus to next or previous input
	const focusInput = (index: number) => {
		if (index >= 0 && index < length) {
			inputs[index]?.focus();
		}
	};

	// Handle key input
	const handleInput = (e: Event, index: number) => {
		const input = e.target as HTMLInputElement;
		const value = input.value.replace(/\D/g, ''); // Only digits

		if (value.length > 1) {
			// Handle paste or multiple characters
			const chars = value.split('');
			for (let i = 0; i < chars.length && index + i < length; i++) {
				values[index + i] = chars[i];
			}
			focusInput(index + chars.length);
		} else {
			values[index] = value;
			if (value && index < length - 1) {
				focusInput(index + 1);
			}
		}

		if (values.every(v => v.length === 1)) {
			dispatch('complete', values.join(''));
		}
	};

	// Handle backspace to move focus
	const handleKeyDown = (e: KeyboardEvent, index: number) => {
		if (e.key === 'Backspace' && values[index] === '' && index > 0) {
			values[index - 1] = '';
			focusInput(index - 1);
		}
	};

	onMount(() => {
		focusInput(0);
	});
</script>

<div class="flex justify-center gap-2">
	{#each Array(length) as _, i}
		<input
	
			class="w-12 h-12 text-center text-lg rounded-md bg-slate-800 text-white border border-slate-700 focus:ring-2 focus:ring-cyan-500 focus:outline-none font-mono"
			type="text"
			maxlength="1"
			inputmode="numeric"
			pattern="[0-9]*"
			autocomplete="one-time-code"
			on:input={(e) => handleInput(e, i)}
			on:keydown={(e) => handleKeyDown(e, i)}
		/>
	{/each}
</div>
