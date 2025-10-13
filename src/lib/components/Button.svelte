<script lang="ts">
	export let variant: 'primary' | 'secondary' | 'outline' = 'primary';
	export let type: 'button' | 'submit' | 'reset' = 'button';
	export let disabled = false;

	const base = "px-4 py-2 rounded-md font-medium transition-colors shadow-sm";
	const styles = {
		primary: "bg-primary-600 text-white hover:bg-primary-700 focus:ring-primary-500",
		secondary: "bg-secondary-100 text-neutral-800 hover:bg-secondary-200 focus:ring-secondary-400",
		outline: "border border-neutral-300 text-neutral-700 hover:bg-neutral-100"
	};
</script>

<button
	type={type}
	disabled={disabled}
	class={`${base} ${styles[variant]} ${disabled ? 'opacity-60 cursor-not-allowed' : ''}`}
>
	<slot />
</button>