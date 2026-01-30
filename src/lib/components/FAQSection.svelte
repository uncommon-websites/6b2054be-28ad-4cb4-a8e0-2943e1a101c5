<script lang="ts">
  let openIndex: number | null = null;

  const faqs = [
    { question: "How quickly can I create my digital clone?", answer: "You can have your clone up and running in 30 seconds. Just upload your existing content (YouTube videos, podcasts, articles) and Delphi trains your clone automatically." },
    { question: "Will my clone sound like me?", answer: "Yes. Your clone is trained on your actual words and speaking style. It never improvises or makes up answers—it only speaks what you've already said or written." },
    { question: "Is my data private and secure?", answer: "Absolutely. Your digital mind is fully encrypted, never shared or sold. You maintain complete ownership and control over your clone forever." },
    { question: "What languages does Delphi support?", answer: "Delphi supports 40+ languages, allowing your clone to answer questions in your audience's native language automatically." },
    { question: "Can I monetize my digital clone?", answer: "Yes. On the Immortal tier, you can charge for access to your clone, creating a scalable revenue stream from your expertise." },
    { question: "How does Delphi compare to hiring a virtual assistant?", answer: "Unlike a VA, your Delphi clone speaks in your authentic voice, handles unlimited conversations simultaneously, works 24/7, and costs a fraction of the price." },
    { question: "What types of content can I use to train my clone?", answer: "You can train your clone on YouTube videos, podcasts, articles, books, social media posts, and any written or recorded content you've created." },
    { question: "Can I integrate my clone into my website or app?", answer: "Yes. Delphi offers website embedding, SMS, WhatsApp, Slack integration, and API access for custom applications." },
    { question: "Who uses Delphi?", answer: "Coaches, experts, thought leaders, and content creators like Jay Shetty, Matthew Hussey, Lenny Rachitsky, and Vanessa Van Edwards use Delphi to scale their personalized advice." },
    { question: "What's the difference between the pricing tiers?", answer: "Plans differ by training capacity (how much content you can upload), contact limits, integrations, and features like analytics, CRM syncing, and monetization capabilities." },
    { question: "Can I try Delphi for free?", answer: "Yes. Our free tier includes 100k training words, 100 contacts, voice & video chat, and website embedding—perfect for testing your clone." },
    { question: "How accurate are the responses from my clone?", answer: "Your clone only uses information from your training content. It won't make up answers or speak beyond what you've taught it, ensuring authenticity and accuracy." }
  ];

  function toggle(index: number) {
    openIndex = openIndex === index ? null : index;
  }
</script>

<section id="help" class="py-20 bg-white">
  <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="mb-12">
      <h2 class="text-3xl font-bold text-gray-900 mb-4">Frequently asked questions</h2>
      <p class="text-gray-500">Everything you need to know about creating your digital clone and scaling your wisdom with Delphi.</p>
    </div>

    <div class="divide-y divide-gray-100 border-t border-gray-100">
      {#each faqs as faq, i}
        <div class="py-4">
          <button 
            class="w-full flex justify-between items-center text-left focus:outline-none group"
            on:click={() => toggle(i)}
          >
            <span class="text-sm font-medium text-gray-900 group-hover:text-gray-600 transition-colors">{faq.question}</span>
            <span class="ml-6 flex-shrink-0">
              <svg class={`w-4 h-4 text-gray-400 transform transition-transform ${openIndex === i ? 'rotate-180' : ''}`} fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
              </svg>
            </span>
          </button>
          {#if openIndex === i}
            <div class="mt-2 pr-12">
              <p class="text-sm text-gray-500">{faq.answer}</p>
            </div>
          {/if}
        </div>
      {/each}
    </div>
  </div>
</section>
