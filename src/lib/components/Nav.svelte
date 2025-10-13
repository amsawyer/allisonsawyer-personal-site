<script lang="ts">
    import ModeToggle from '$lib/components/ModeToggle.svelte';

    export let title: string = "Home";
	export let links: { name: string; href: string }[] = [
		{ name: "Resume", href: "/resume" },
		{ name: "Mountains", href: "/mountains" }
	];
	let isOpen = false;
</script>

<nav class="navbar">
	<div class="max-w-7xl mx-auto flex justify-between items-center p-4">
	    <a href="/" class="navbartitletext">{title}</a>

		<!-- Desktop links -->
		<div class="hidden md:flex space-x-6">
			{#each links as link}
				<a href={link.href} class="navbartext">
					{link.name}
				</a>
			{/each}

            <ModeToggle />
		</div>

		<!-- Mobile menu button -->
		<button class="md:hidden text-neutral-700" on:click={() => (isOpen = !isOpen)}>
			<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
				stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
				<path stroke-linecap="round" stroke-linejoin="round"
					d="M3.75 5.25h16.5M3.75 12h16.5m-16.5 6.75h16.5" />
			</svg>
		</button>
	</div>

	<!-- Mobile dropdown -->
	{#if isOpen}
		<div class="md:hidden bg-neutral-50 border-t border-neutral-200">
			{#each links as link}
				<a href={link.href} class="block px-4 py-2 text-neutral-700 hover:bg-neutral-100">
					{link.name}
				</a>
			{/each}
		</div>
	{/if}
</nav>