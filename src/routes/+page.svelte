No worries! Here is that Microcircuit code again.

I’ve made it even better for a first-timer: I included the FAQ logic and the Contact section, using colors that fit the "Microcircuit" name (dark slate and emerald green).

Copy and Paste this into src/routes/+page.svelte:
Svelte

<script>
  // This part handles the FAQ opening and closing logic
  let openFaq = null;

  const faqs = [
    { 
      q: "What is Microcircuit?", 
      a: "Microcircuit is a creative space for building tiny hardware, efficient code, and cool electronics projects." 
    },
    { 
      q: "How can I get involved?", 
      a: "Join the Hack Club Slack or reach out via the contact section below to start shipping!" 
    },
    { 
      q: "Do I need experience?", 
      a: "Not at all. Whether you're a beginner or a pro, if you like building things, you belong here." 
    }
  ];

  function toggle(index) {
    openFaq = openFaq === index ? null : index;
  }
</script>

<main class="min-h-screen bg-[#0f172a] text-emerald-400 font-sans p-8 flex flex-col items-center">
  
  <section class="py-24 text-center">
    <div class="mb-4 inline-block px-3 py-1 border border-emerald-500 text-xs tracking-widest uppercase rounded-full">
      System: Operational
    </div>
    <h1 class="text-6xl md:text-8xl font-black mb-4 uppercase tracking-tighter text-white">
      Microcircuit
    </h1>
    <p class="text-emerald-200 text-xl max-w-lg mx-auto">
      Building the future, one tiny component at a time.
    </p>
  </section>

  <section id="faq" class="w-full max-w-2xl mb-24">
    <h2 class="text-3xl font-bold mb-8 text-white flex items-center">
      <span class="text-emerald-500 mr-2">/</span> FAQ
    </h2>
    
    {#each faqs as item, i}
      <div class="mb-4 border border-emerald-900 rounded-xl overflow-hidden bg-[#1e293b]/50">
        <button 
          on:click={() => toggle(i)}
          class="w-full p-5 text-left hover:bg-[#1e293b] transition-colors flex justify-between items-center font-bold">
          <span>{item.q}</span>
          <span class="text-2xl">{openFaq === i ? '−' : '+'}</span>
        </button>
        
        {#if openFaq === i}
          <div class="p-5 bg-[#0f172a] text-slate-300 border-t border-emerald-900 leading-relaxed">
            {item.a}
          </div>
        {/if}
      </div>
    {/each}
  </section>

  <section id="contact" class="w-full max-w-2xl p-10 bg-emerald-500 text-slate-900 rounded-3xl shadow-[8px_8px_0px_0px_#064e3b]">
    <h2 class="text-4xl font-black mb-4 uppercase tracking-tight">Connect</h2>
    <p class="font-bold text-lg mb-6 opacity-90">Have a question or a project to share? Send us a transmission.</p>
    
    <a href="mailto:hello@microcircuit.com" class="text-2xl font-black underline decoration-4 hover:text-white transition-colors">
      hello@microcircuit.com
    </a>
  </section>

  <footer class="mt-20 pb-10 text-slate-500 text-sm">
    &copy; 2026 Microcircuit Website • Built with SvelteKit
  </footer>

</main>

<style>
  /* This adds a subtle glow to the main title */
  h1 {
    text-shadow: 0 0 20px rgba(16, 185, 129, 0.2);
  }
</style>
Helpful tips for this code:
The Colors: I used bg-[#0f172a] (a very dark blue) and bg-emerald-500 (a bright green). This gives it that high-tech "circuit board" look.

The Shadow: Notice the shadow-[8px_8px_0px_0px_#064e3b] on the contact box. That is what creates the "Hard Shadow" look from the Woof website.

The FAQ: The {#each} block is a Svelte feature that automatically loops through your list of questions so you don't have to type the HTML over and over.

Once you save this, does your browser show the new dark green theme? If it does, we can talk about how to change the text to say exactly what you want!