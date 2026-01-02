<script>
  // This is your data list for the FAQ
  const faqs = [
    { q: "What is Microcircuit?", a: "Microcircuit is a YSWS where teenagers design circuits and ship them to get grants to solder and assemble them together them together!" },
    { q: "How do I join?", a: 'Join <a href="https://app.slack.com/client/E09V59WQY1E/C0A5FDD7AHM" target="_blank" rel="noopener noreferrer" style="text-decoration:underline; font-weight:700;">#microcircuit</a> on the Hack Club Slack and fill out this <a href="https://iceverychill.fillout.com/microcircuits" target="_blank" rel="noopener noreferrer" style="text-decoration:underline; font-weight:700;">form</a> to RSVP' },
    { q: "Do I need experience?", a: "Not at all, anyone can join!" },
    { q: "When will this launch?", a: "we are still working on this, stay tuned for updates!" },
    { q: "How will it work?", a: "Teenager's between 13-18 will create a repository and upload a schematic, BOM and read.me about there project. Then they will recive a grant to buy the part for their build and solder it together to get sparks a currency which can be exchanged for thing to help you build and more cool stuff!" },
  ];
  let openIndex = -1;
  /** @param {number} i */
  const toggle = (i) => {
    openIndex = openIndex === i ? -1 : i;
  };
  let contactOpen = false;
  const toggleContact = () => contactOpen = !contactOpen;
  let slackOpen = false;
  let emailOpen = false;
  const toggleSlack = () => slackOpen = !slackOpen;
  const toggleEmail = () => emailOpen = !emailOpen;
</script>

<svelte:head>
  <title>Microcircuit</title>
</svelte:head>

<main class="min-h-screen bg-[#022c22] text-[#ecfdf5] font-mono p-8">
  <header class="max-w-4xl mx-auto text-center py-20 border-4 border-[#064e3b] bg-[#065f46] shadow-[8px_8px_0px_0px_#047857]">
    <h1 class="text-6xl font-black uppercase tracking-tighter mb-4">Microcircuit</h1>
    <p class="text-xl opacity-90">Design a circuit, get a grant to solder it together!</p>
  </header>

  <section class="max-w-2xl mx-auto mt-16">
    <h2 class="text-5xl font-bold mb-8 text-[#10b981] text-center">FAQ</h2>
    <div class="space-y-4">
      {#each faqs as faq, i}
        <div class="border-2 border-[#064e3b] bg-[#065f46]">
          <button
            type="button"
            on:click={() => toggle(i)}
            class="w-full flex items-center justify-between p-4 text-left"
            aria-expanded={openIndex === i}
          >
            <span class="font-bold text-[#34d399]">Q: {faq.q}</span>
            <span class="text-2xl text-[#34d399]">{openIndex === i ? '−' : '+'}</span>
          </button>
          {#if openIndex === i}
            <div class="px-4 pb-4 text-sm opacity-80">
              {@html faq.a}
            </div>
          {/if}
        </div>
      {/each}
    </div>
  </section>

  <footer class="max-w-md mx-auto mt-20 p-8 border-4 border-[#064e3b] bg-transparent shadow-[8px_8px_0px_0px_#064e3b] text-center">
    <div class="border-2 border-[#064e3b] bg-[#065f46]">
      <button type="button" on:click={toggleContact} class="w-full flex items-center justify-between p-4" aria-expanded={contactOpen}>
        <h3 class="text-2xl font-bold mb-0 text-[#10b981]">Get in Touch</h3>
        <span class="text-2xl text-[#34d399]">{contactOpen ? '−' : '+'}</span>
      </button>
      {#if contactOpen}
        <div class="px-4 pb-4 mt-4 text-sm opacity-80 text-left space-y-4">
          <div class="border-2 border-[#064e3b] bg-[#065f46]">
            <button type="button" on:click={toggleSlack} class="w-full flex items-center justify-between p-4" aria-expanded={slackOpen}>
              <span class="font-bold text-[#34d399]">Slack</span>
              <span class="text-2xl text-[#34d399]">{slackOpen ? '−' : '+'}</span>
            </button>
            {#if slackOpen}
              <div class="px-4 pb-4 text-sm opacity-80">
                <p>Have questions, DM <a href="https://app.slack.com/client/E09V59WQY1E/dms" target="_blank" rel="noopener noreferrer" style="text-decoration:underline; font-weight:700;">@PenguinMo</a></p>
              </div>
            {/if}
          </div>

          <div class="border-2 border-[#064e3b] bg-[#065f46]">
            <button type="button" on:click={toggleEmail} class="w-full flex items-center justify-between p-4" aria-expanded={emailOpen}>
              <span class="font-bold text-[#34d399]">Email</span>
              <span class="text-2xl text-[#34d399]">{emailOpen ? '−' : '+'}</span>
            </button>
            {#if emailOpen}
              <div class="px-4 pb-4 text-sm opacity-80">
                <p>Send us an email: <a href="mailto:mkinteh2012@gmail.com" style="text-decoration:underline; font-weight:700;">mkinteh2012@gmail.com</a></p>
              </div>
            {/if}
          </div>
        </div>
      {/if}
    </div>
  </footer>
</main>

<style>
  /* This ensures the font feels "hackery" */
  :global(body) {
    margin: 0;
    padding: 0;
  }
</style>