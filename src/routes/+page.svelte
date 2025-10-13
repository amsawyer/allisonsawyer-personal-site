<script lang="ts">
    import Icon from "@iconify/svelte";
	import Nav from '$lib/components/Nav.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import Card from '$lib/components/Card.svelte';
	import Button from '$lib/components/Button.svelte';

	let headshot = "/files/headshot.jpg";
	const links = [
        { name: "GitHub", href: "https://github.com/amsawyer", icon: "mdi:github" },
        { name: "LinkedIn", href: "https://www.linkedin.com/in/allison-sawyer-55763289/", icon: "mdi:linkedin" }
    ];
</script>

<div class="min-h-screen flex flex-col">
    <Nav />

    <main class="flex-grow">
        <section class="max-w-5xl mx-auto text-center py-[var(--spacing-section)] px-4">
            <div class="flex flex-col sm:flex-row items-center sm:items-start gap-30">
                <!-- Headshot -->
                <img src={headshot} class="w-40 h-40 object-cover rounded-full" alt="Profile picture" />
                <!-- TODO light/dark mode switch -->

                <!-- Intro text -->
                <div class="text-center sm:text-left">
                    <h1 class="my-4">Allison Sawyer</h1>
                    <h2 class="mb-4">Cybersecurity Engineer, CISSP, GCFA, GCFE</h2>
                    <div class="flex gap-8">
                      self [at] allisonsawyer [dot] com
                      {#each links as link}
                        <a href={link.href} target="_blank" rel="noopener noreferrer" aria-label={link.name}>
                          <Icon icon={link.icon} class="text-2xl" />
                        </a>
                      {/each}
                    </div>
                    <!-- <Icon icon="mdi:github" /><Icon icon="mdi:linkedin" />-->
                </div>
            </div>
            <p class="mt-14 max-w-4xl mx-auto text-center">
                <em>Helping organizations strengthen their security operations through automation and a risk-based, data-driven approach.</em>
            </p>
        </section>

        <section class="max-w-6xl mx-auto grid sm:grid-cols-2 lg:grid-cols-3 gap-8 px-4 py-[var(--spacing-component)]">
            <Card title="My Work"
                description="I currently work as a **Principal Customer Success Engineer** at **Palo Alto Networks**, where I help our clients save time and reduce manual workload by leveraging our Cortex solutions." />
            <Card title="My Interests"
                description="My interests include:
 - Security and privacy policy
 - Applications of ML and automation to security operations
 - Digital forensics" />
            <Card title="My Skills"
                description="My skills include:
 - SOAR
 - Python
 - Digital forensics
 - (See my <a href='/resume'>resume</a> for more)" />
        </section>
    </main>

    <Footer />
</div>