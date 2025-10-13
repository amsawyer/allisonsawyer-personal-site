<script lang="ts">
	import Nav from '$lib/components/Nav.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import Card from '$lib/components/Card.svelte';
	import Button from '$lib/components/Button.svelte';
</script>

<div class="min-h-screen flex flex-col">
    <Nav />

    <main class="flex-grow">
        <section class="max-w-5xl mx-auto py-[var(--spacing-section)] px-4">
            <p>I like to spend my weekends in the mountains whenever possible. <a href="https://www.peakbagger.com/climber/ClimbListC.aspx?cid=40468">My Peakbagger Ascent List</a>
            <h2 class="my-4">Summit Map</h2>
            <iframe src="https://caltopo.com/m/J010SRG" class="w-full h-[75vh]" title="Summits Map"></iframe>
        </section>
    </main>

    <Footer />
</div>