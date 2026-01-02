<script>
  // This is your data list for the FAQ
  const faqs = [
    { q: "What is Microcircuit?", a: "We are a student-led initiative focused on electronics and hardware hacking." },
    { q: "How do I join?", a: "Check out our GitHub or join the Hack Club Slack to get involved!" },
    { q: "Do I need experience?", a: "Not at all! We're all about learning by doing." }
  ];
</script>

<svelte:head>
  <title>Microcircuit</title>
</svelte:head>

<main class="min-h-screen bg-[#022c22] text-[#ecfdf5] font-mono p-8">
  <header class="max-w-4xl mx-auto text-center py-20 border-4 border-[#064e3b] bg-[#065f46] shadow-[8px_8px_0px_0px_#047857]">
    <h1 class="text-6xl font-black uppercase tracking-tighter mb-4">Microcircuit</h1>
    <p class="text-xl opacity-90">Building the hardware of tomorrow, today.</p>
  </header>

  <section class="max-w-2xl mx-auto mt-16">
    <h2 class="text-3xl font-bold mb-8 text-[#10b981]">Common Questions</h2>
    <div class="space-y-4">
      {#each faqs as faq}
        <div class="p-4 border-2 border-[#064e3b] bg-[#065f46]">
          <p class="font-bold text-[#34d399]">Q: {faq.q}</p>
          <p class="mt-2 opacity-80">{faq.a}</p>
        </div>
      {/each}
    </div>
  </section>

  <footer class="max-w-md mx-auto mt-20 p-8 border-4 border-[#064e3b] bg-[#065f46] shadow-[8px_8px_0px_0px_#064e3b] text-center">
    <h3 class="text-2xl font-bold mb-4">Get in Touch</h3>
    <p class="mb-6">Ready to start building?</p>
    <a href="mailto:hello@microcircuit.hackclub.com" 
       class="inline-block bg-[#10b981] text-[#022c22] px-6 py-3 font-bold hover:bg-[#34d399] transition-colors">
      Email Us
    </a>
  </footer>
</main>

<style>
  /* This ensures the font feels "hackery" */
  :global(body) {
    margin: 0;
    padding: 0;
  }
</style>