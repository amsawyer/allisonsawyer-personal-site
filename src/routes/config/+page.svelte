<script>
 // Color scales from the configuration
 const colorScales = [
  {
   name: 'Primary (Navy Blue)',
   description: 'Conveys trust, professionalism, cybersecurity',
   prefix: 'primary',
   mainColor: '500'
  },
  {
   name: 'Secondary (Warm Gray)',
   description: 'Neutral tone for secondary info, background cards',
   prefix: 'secondary',
   mainColor: '500'
  },
  {
   name: 'Accent (Cyan)',
   description: 'For highlights, icons, small details',
   prefix: 'accent',
   mainColor: '500'
  },
  {
   name: 'Neutral (Cool Gray)',
   description: 'For text, base background',
   prefix: 'neutral',
   mainColor: '500'
  },
  {
   name: 'Danger (Red)',
   description: 'Used minimally (e.g., form validation errors)',
   prefix: 'danger',
   mainColor: '500'
  }
 ];

 const colorValues = [50, 100, 200, 300, 400, 500, 600, 700, 800, 900, 950];

 const typographyExamples = [
  { tag: 'h1', text: 'Heading 1 - Primary 500, 4xl, Bold' },
  { tag: 'h2', text: 'Heading 2 - Primary 400, 3xl, Semibold' },
  { tag: 'h3', text: 'Heading 3 - Neutral 100, 2xl, Semibold' },
  { tag: 'h4', text: 'Heading 4 - Neutral 200, xl, Medium' },
  { tag: 'h5', text: 'Heading 5 - Neutral 300, lg, Medium' },
  { tag: 'p', text: 'Paragraph - Base size, relaxed leading, Neutral 300' },
  { tag: 'a', text: 'Link - Secondary 400, underlined' },
  { tag: 'code', text: 'Code - Accent 400, JetBrains Mono font' }
 ];

 const spacingValues = [
  { name: 'Section', variable: 'spacing-section', description: 'For major sections' },
  { name: 'Component', variable: 'spacing-component', description: 'Between components' },
  { name: 'Element', variable: 'spacing-element', description: 'Between elements' }
 ];

 const radiusValues = [
  { name: 'Small', class: 'rounded-sm' },
  { name: 'Medium', class: 'rounded-md' },
  { name: 'Large', class: 'rounded-lg' }
 ];

 const shadowValues = [
  { name: 'Small', class: 'shadow-sm', description: '0 1px 2px 0 rgba(0, 0, 0, 0.05)' },
  { name: 'Medium', class: 'shadow-md', description: '0 4px 6px -1px rgba(0, 0, 0, 0.1)' },
  { name: 'Large', class: 'shadow-lg', description: '0 10px 15px -3px rgba(0, 0, 0, 0.1)' }
 ];
</script>

<!--
Safelist: These classes are used dynamically and need to be included in the build:
bg-primary-50 bg-primary-100 bg-primary-200 bg-primary-300 bg-primary-400 bg-primary-500 bg-primary-600 bg-primary-700 bg-primary-800 bg-primary-900 bg-primary-950
bg-secondary-50 bg-secondary-100 bg-secondary-200 bg-secondary-300 bg-secondary-400 bg-secondary-500 bg-secondary-600 bg-secondary-700 bg-secondary-800 bg-secondary-900 bg-secondary-950
bg-accent-50 bg-accent-100 bg-accent-200 bg-accent-300 bg-accent-400 bg-accent-500 bg-accent-600 bg-accent-700 bg-accent-800 bg-accent-900 bg-accent-950
bg-neutral-50 bg-neutral-100 bg-neutral-200 bg-neutral-300 bg-neutral-400 bg-neutral-500 bg-neutral-600 bg-neutral-700 bg-neutral-800 bg-neutral-900 bg-neutral-950
bg-danger-50 bg-danger-100 bg-danger-200 bg-danger-300 bg-danger-400 bg-danger-500 bg-danger-600 bg-danger-700 bg-danger-800 bg-danger-900 bg-danger-950
-->

<svelte:head>
 <title>Tailwind Configuration Showcase</title>
</svelte:head>

<div class="min-h-screen bg-neutral-950 px-4 py-12">
 <div class="mx-auto max-w-7xl">
  <!-- Header -->
  <div class="mb-16 text-center">
   <h1 class="mb-4">Tailwind Configuration Showcase</h1>
   <p class="mx-auto max-w-3xl text-xl text-neutral-400">
    A comprehensive overview of your custom Tailwind theme including colors, typography,
    spacing, borders, and shadows.
   </p>
  </div>

  <!-- Color Scales Section -->
  <section class="mb-16">
   <h2 class="mb-8">Color Scales</h2>
   <div class="grid gap-8">
    {#each colorScales as scale}
     <div class="rounded-lg bg-neutral-900 p-6">
      <div class="mb-4">
       <h3 class="mb-2">{scale.name}</h3>
       <p class="text-neutral-400">{scale.description}</p>
      </div>
      <div class="grid grid-cols-2 gap-2 sm:grid-cols-4 md:grid-cols-6 lg:grid-cols-11">
       {#each colorValues as value}
        <div class="text-center">
         <div
          class="mb-2 h-16 w-full rounded-md border border-neutral-700 bg-{scale.prefix}-{value}"
          class:ring-2={value.toString() === scale.mainColor}
          class:ring-white={value.toString() === scale.mainColor}
         ></div>
         <div class="text-xs text-neutral-400">{value}</div>
         <div class="text-xs text-neutral-500">{scale.prefix}-{value}</div>
        </div>
       {/each}
      </div>
     </div>
    {/each}
   </div>
  </section>

  <!-- Typography Section -->
  <section class="mb-16">
   <h2 class="mb-8">Typography</h2>
   <div class="rounded-lg bg-neutral-900 p-6">
    <div class="grid gap-6">
     {#each typographyExamples as example}
      <div class="border-b border-neutral-800 pb-4 last:border-b-0">
       <svelte:element this={example.tag}>
        {example.text}
        {#if example.tag === 'a'}
         <span class="ml-2 text-sm text-neutral-500">(hover to see color change)</span>
        {/if}
       </svelte:element>
       <div class="mt-1 text-sm text-neutral-500">
        &lt;{example.tag}&gt; element styling
       </div>
      </div>
     {/each}

     <!-- Font Family Examples -->
     <div class="mt-8 border-t border-neutral-800 pt-8">
      <h4 class="mb-4">Font Families</h4>
      <div class="grid gap-4">
       <div>
        <p class="font-sans">
         Sans-serif font (Inter): The quick brown fox jumps over the lazy dog
        </p>
        <div class="text-sm text-neutral-500">
         font-sans: Inter, ui-sans-serif, system-ui
        </div>
       </div>
       <div>
        <p class="font-mono">
         Monospace font (JetBrains Mono): The quick brown fox jumps over the lazy dog
        </p>
        <div class="text-sm text-neutral-500">
         font-mono: JetBrains Mono, ui-monospace, Courier New
        </div>
       </div>
      </div>
     </div>
    </div>
   </div>
  </section>

  <!-- Spacing Section -->
  <section class="mb-16">
   <h2 class="mb-8">Custom Spacing</h2>
   <div class="rounded-lg bg-neutral-900 p-6">
    <div class="grid gap-6">
     {#each spacingValues as spacing}
      <div>
       <h4 class="mb-2">{spacing.name} Spacing</h4>
       <p class="mb-3 text-neutral-400">{spacing.description}</p>
       <div
        class="bg-primary-500 flex items-center justify-center rounded-md font-medium text-white"
        style="background-color: var(--color-primary-500); height: var(--{spacing.variable})"
       >
        {spacing.variable}
       </div>
      </div>
     {/each}
    </div>
   </div>
  </section>

  <!-- Border Radius Section -->
  <section class="mb-16">
   <h2 class="mb-8">Border Radius</h2>
   <div class="rounded-lg bg-neutral-900 p-6">
    <div class="grid grid-cols-1 gap-6 md:grid-cols-3">
     {#each radiusValues as radius}
      <div class="text-center">
       <h4 class="mb-3">{radius.name}</h4>
       <div
        class="mx-auto mb-2 flex h-24 w-24 items-center justify-center font-medium text-white {radius.class}"
        style="background-color: var(--color-secondary-500)"
       ></div>
       <div class="text-sm text-neutral-400">{radius.class}</div>
      </div>
     {/each}
    </div>
   </div>
  </section>

  <!-- Shadows Section -->
  <section class="mb-16">
   <h2 class="mb-8">Shadows</h2>
   <div class="rounded-lg bg-neutral-900 p-6">
    <div class="grid grid-cols-1 gap-8 md:grid-cols-3">
     {#each shadowValues as shadow}
      <div class="text-center">
       <h4 class="mb-3">{shadow.name}</h4>
       <div
        class="mx-auto h-24 w-24 rounded-lg bg-neutral-100 {shadow.class} mb-3 flex items-center justify-center font-medium text-neutral-900"
       >
        {shadow.class}
       </div>
       <div class="text-xs break-all text-neutral-400">{shadow.description}</div>
      </div>
     {/each}
    </div>
   </div>
  </section>

  <!-- Interactive Examples Section -->
  <section class="mb-16">
   <h2 class="mb-8">Interactive Elements</h2>
   <div class="rounded-lg bg-neutral-900 p-6">
    <div class="grid gap-8">
     <!-- Buttons -->
     <div>
      <h4 class="mb-4">Button Variations</h4>
      <div class="flex flex-wrap gap-4">
       <button
        class="rounded-md px-6 py-3 font-medium text-white transition-colors hover:opacity-90"
        style="background-color: var(--color-primary-500)"
       >
        Primary Button
       </button>
       <button
        class="rounded-md px-6 py-3 font-medium text-white transition-colors hover:opacity-90"
        style="background-color: var(--color-secondary-500)"
       >
        Secondary Button
       </button>
       <button
        class="rounded-md px-6 py-3 font-medium text-white transition-colors hover:opacity-90"
        style="background-color: var(--color-accent-500)"
       >
        Accent Button
       </button>
       <button
        class="rounded-md border-2 bg-transparent px-6 py-3 font-medium transition-colors hover:opacity-75"
        style="border-color: var(--color-primary-500); color: var(--color-primary-400)"
       >
        Outline Button
       </button>
      </div>
     </div>

     <!-- Cards -->
     <div>
      <h4 class="mb-4">Card Examples</h4>
      <div class="grid grid-cols-1 gap-6 md:grid-cols-3">
       <div class="rounded-lg bg-neutral-800 p-6 shadow-sm">
        <h5 class="mb-2">Small Shadow Card</h5>
        <p>This card uses shadow-sm for subtle depth.</p>
       </div>
       <div class="rounded-lg bg-neutral-800 p-6 shadow-md">
        <h5 class="mb-2">Medium Shadow Card</h5>
        <p>This card uses shadow-md for moderate depth.</p>
       </div>
       <div class="rounded-lg bg-neutral-800 p-6 shadow-lg">
        <h5 class="mb-2">Large Shadow Card</h5>
        <p>This card uses shadow-lg for prominent depth.</p>
       </div>
      </div>
     </div>

     <!-- Form Elements -->
     <div>
      <h4 class="mb-4">Form Elements</h4>
      <div class="grid grid-cols-1 gap-6 md:grid-cols-2">
       <div>
        <label class="mb-2 block text-sm font-medium" for="sample-input">Sample Input</label
        >
        <input
         id="sample-input"
         type="text"
         placeholder="Focus to see the ring effect"
         class="w-full rounded-md border border-neutral-600 bg-neutral-800 px-4 py-2 text-neutral-100 placeholder-neutral-400"
        />
       </div>
       <div>
        <label class="mb-2 block text-sm font-medium" for="sample-select"
         >Sample Select</label
        >
        <select
         id="sample-select"
         class="w-full rounded-md border border-neutral-600 bg-neutral-800 px-4 py-2 text-neutral-100"
        >
         <option>Option 1</option>
         <option>Option 2</option>
         <option>Option 3</option>
        </select>
       </div>
      </div>
     </div>
    </div>
   </div>
  </section>

  <!-- Code Examples Section -->
  <section>
   <h2 class="mb-8">Usage Examples</h2>
   <div class="rounded-lg bg-neutral-900 p-6">
    <h4 class="mb-4">Sample CSS Classes</h4>
    <pre><code
      >{`<!-- Color Classes -->
<div class="bg-primary-500 text-white">Primary background</div>
<div class="bg-secondary-400 text-white">Secondary background</div>
<div class="text-accent-500">Accent text</div>
<div class="border-danger-500">Danger border</div>

<!-- Typography -->
<h1>Auto-styled heading 1</h1>
<p>Auto-styled paragraph</p>
<code>Auto-styled code</code>

<!-- Spacing -->
<div class="p-[var(--spacing-component)]">Component padding</div>
<div class="mb-[var(--spacing-section)]">Section margin</div>

<!-- Radius -->
<div class="rounded-sm">Small radius</div>
<div class="rounded-md">Medium radius</div>
<div class="rounded-lg">Large radius</div>`}</code
     ></pre>
   </div>
  </section>
 </div>
</div>