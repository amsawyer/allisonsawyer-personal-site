<script lang="ts">
	import { marked } from 'marked';

	export let title: string;
	export let description: string = "";
	export let image: string = "";
</script>

<div class="card">
	{#if image}
		<img src={image} alt={title} class="w-full h-48 object-cover" />
	{/if}

	<div class="p-6">
		<h3>{title}</h3>

		<!-- Slot override; markdown fallback -->
		<div class="leading-relaxed">
			<slot>
				{@html marked(description, { breaks : true })}
			</slot>
		</div>
	</div>
</div>