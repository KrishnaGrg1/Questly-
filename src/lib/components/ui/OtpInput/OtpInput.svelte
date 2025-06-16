<script lang="ts">
    import { onMount } from 'svelte';

    export let length = 6;
    let otp: string[] = Array(length).fill('');
    let inputs: HTMLInputElement[] = [];

    // Focus first input on mount
    onMount(() => {
        if (inputs[0]) inputs[0].focus();
    });

    const handleInput = (e: Event, index: number) => {
        const target = e.target as HTMLInputElement;
        let value = target.value;

        otp = [...otp];
        otp[index] = value.slice(-1); // Only take last character
        target.value = otp[index];

        // Move to next input
        if (value && index < length - 1) {
            inputs[index + 1]?.focus();
        }

        dispatch('complete', otp.join(''));
    };

    const handleKeyDown = (e: KeyboardEvent, index: number) => {
        const target = e.target as HTMLInputElement;

        // Backspace and previous input
        if (e.key === 'Backspace' && !otp[index] && index > 0) {
            inputs[index - 1]?.focus();
        }
    };

    const handlePaste = (e: ClipboardEvent) => {
        e.preventDefault();
        const data = e.clipboardData.getData('text').slice(0, length);
        for (let i = 0; i < length; i++) {
            if (i < data.length && /\d/.test(data[i])) {
                otp[i] = data[i];
                inputs[i]?.focus();
            } else {
                break;
            }
        }
    };

    $: joinedOtp = otp.join('');

</script>

<div class="flex justify-center gap-3 mb-4" on:paste={handlePaste}>
    {#each otp as _, index (index)}
        <input
            bind:this={inputs[index]}
            type="text"
            inputmode="numeric"
            maxlength="1"
            class="w-12 h-14 text-center text-xl font-mono bg-slate-800/50 border border-slate-700 rounded-lg text-white focus:border-indigo-500 outline-none transition-all duration-200"
            on:input={(e) => handleInput(e, index)}
            on:keydown={(e) => handleKeyDown(e, index)}
        />
    {/each}
</div>

<!-- Optional hidden input for form submission -->
<input type="hidden" name="otp" value={joinedOtp} />

<style>
    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }
</style>