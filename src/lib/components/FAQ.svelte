<script lang="ts">
  import { slide } from 'svelte/transition';
  
  interface FAQItem {
    question: string;
    answer: string;
  }

  const faqs: FAQItem[] = [
    { question: "How is BlendFi different from other finance apps?", answer: "BlendFi is the first platform to truly unify traditional banking, cryptocurrency management, and startup investing in one place. Instead of juggling multiple apps with different logins, fees, and interfaces, you get one seamless experience with radical transparency—no hidden fees, no confusing jargon." },
    { question: "Is my money safe with BlendFi?", answer: "Absolutely. We use bank-grade security with multi-factor biometric authentication and advanced encryption protocols. For crypto, we offer non-custodial wallet options, meaning you maintain full control of your assets. Our platform is built on Orobit blockchain technology for enhanced security and efficiency." },
    { question: "What cryptocurrencies does BlendFi support?", answer: "BlendFi supports 50+ major cryptocurrencies including Bitcoin, Ethereum, and many others. You can buy, sell, trade, and hold all your crypto assets in one secure, non-custodial wallet with complete transparency on all transactions and fees." },
    { question: "What's the minimum investment for startups?", answer: "We've democratized early-stage investing with a minimum investment of just $100. All startup opportunities are carefully vetted by our team to ensure quality and potential, making it accessible for everyone to participate in the next generation of innovation." },
    { question: "Are there any hidden fees?", answer: "No. Radical transparency is one of our core values. All fees are clearly displayed upfront before any transaction. We believe in honest, straightforward pricing with no surprises—ever." },
    { question: "When will BlendFi be available?", answer: "We're currently in early access phase and actively collecting sign-ups for our launch. Join our waitlist to be among the first to experience unified finance and get notified as soon as we open to the public." },
    { question: "What is Orobit blockchain?", answer: "Orobit is the cutting-edge blockchain technology that powers BlendFi, providing enhanced speed, efficiency, and security for all your transactions. It enables us to offer a seamless experience across banking, crypto, and investing while maintaining the highest security standards." }
  ];

  let openIndex: number | null = null;

  function toggle(index: number) {
    openIndex = openIndex === index ? null : index;
  }
</script>

<section id="faq" class="bg-[#f5f5f5] px-6 py-24">
  <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-12 gap-12">
    <div class="lg:col-span-4">
      <h2 class="font-serif text-4xl text-gray-900 mb-6">
        Frequently asked questions
      </h2>
      <a href="mailto:support@blendfi.com" class="text-sm text-gray-900 border-b border-gray-300 pb-0.5 hover:border-black transition-colors">Contact support</a>
    </div>
    
    <div class="lg:col-span-8">
      <div class="border-t border-gray-200">
        {#each faqs as faq, i}
          <div class="border-b border-gray-200">
            <button 
              class="w-full py-6 flex justify-between items-center text-left hover:bg-gray-50 transition-colors"
              on:click={() => toggle(i)}
            >
              <span class="text-lg text-gray-800">{faq.question}</span>
              <span class="text-2xl font-light text-gray-400 ml-4">
                {openIndex === i ? '−' : '+'}
              </span>
            </button>
            {#if openIndex === i}
              <div transition:slide class="pb-6 text-gray-500 leading-relaxed">
                {faq.answer}
              </div>
            {/if}
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>
