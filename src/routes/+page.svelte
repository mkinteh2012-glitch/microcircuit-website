<script>
  // --- 1. THE MAIN HEADERS ---
  const heroTitle = "Microcircuit";
  const heroSubtitle = "Designing the hardware of the future.";

  // --- 2. THE MISSION / ABOUT ---
  const missionTitle = "Our Mission";
  const missionBody = "Microcircuit is a student-led collective focused on open-source hardware. We provide the tools, community, and knowledge to help you move from 'consumer' to 'creator.' Whether it's PCB design, robotics, or vintage tech restoration, we're building it.";

  // --- 3. THE FAQ LIST ---
  // You can add as many as you want here!
  const faqs = [
    { 
      q: "What is this collective?", 
      a: "A community of students obsessed with hardware, electronics, and making things from scratch." 
    },
    { 
      q: "How do I get involved?", 
      a: "Join the Hack Club Slack and look for the #microcircuit channel (coming soon) or start a project on our GitHub." 
    },
    { 
      q: "Do I need to be an engineer?", 
      a: "No. If you can break things and try to fix them, you're one of us." 
    }
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