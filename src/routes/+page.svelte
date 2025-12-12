<script>
  import Navbar from '$lib/components/Navbar.svelte';
  import Hero from '$lib/components/Hero.svelte';
  import Logos from '$lib/components/Logos.svelte';
  import WhyBlendFi from '$lib/components/WhyBlendFi.svelte';
  import Products from '$lib/components/Products.svelte';
  import Security from '$lib/components/Security.svelte';
  import FAQ from '$lib/components/FAQ.svelte';
  import BottomCTA from '$lib/components/BottomCTA.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<div class="min-h-screen bg-[#f5f5f5] font-sans selection:bg-black selection:text-white">
  <Navbar />
  <Hero />
  <Logos />
  <WhyBlendFi />
  <Products />
  <Security />
  <FAQ />
  <BottomCTA />
  <Footer />
</div>

