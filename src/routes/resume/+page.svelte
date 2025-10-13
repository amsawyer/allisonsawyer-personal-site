<script lang="ts">
	import Nav from '$lib/components/Nav.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import Card from '$lib/components/Card.svelte';
	import Button from '$lib/components/Button.svelte';
</script>

<div class="min-h-screen flex flex-col">
    <Nav />

    <main class="flex-grow">
        <section class="max-w-5xl mx-auto py-[var(--spacing-component)] px-4">
            <iframe src="/files/ASawyer-Resume.pdf" type="application/pdf" class="w-full h-[75vh]" title="Resume"></iframe>
        </section>
    </main>

    <Footer />
</div>