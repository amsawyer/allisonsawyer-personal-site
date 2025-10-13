<script lang="ts">
	import { onMount } from 'svelte';

	let darkMode = false;

    // Runs when user first loads page
	onMount(() => {
		// Check stored preference or system default
		const stored = localStorage.getItem('theme');
		if (stored) {
			darkMode = stored === 'dark';
		} else {
			darkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
		}
		document.documentElement.classList.toggle('dark', darkMode);
	});

	function toggleDarkMode() {
		darkMode = !darkMode;
		document.documentElement.classList.toggle('dark', darkMode);
		localStorage.setItem('theme', darkMode ? 'dark' : 'light');
	}
</script>

<button
	on:click={toggleDarkMode}
	class="toggledarkmode"
	aria-label="Toggle dark mode"
>
	<span
		class="togglelightmode"
		style:transform={darkMode ? 'translateX(24px)' : 'translateX(2px)'}
	>
		{#if darkMode}
			☀️
		{:else}
			🌙
		{/if}
	</span>
</button>