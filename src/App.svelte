<script lang="ts">
  import Hero from './components/Hero.svelte';
  import WhyDeo from './components/WhyDeo.svelte';
  import Features from './components/Features.svelte';
  import ComingSoon from './components/ComingSoon.svelte';
  import DemoSection from './components/DemoSection.svelte';
  import SocialProof from './components/SocialProof.svelte';
  import FinalCTA from './components/FinalCTA.svelte';
  import Navigation from './components/Navigation.svelte';
</script>

<Navigation />
<Hero />
<WhyDeo />
<Features />
<ComingSoon />
<DemoSection />
<SocialProof />
<FinalCTA />

<style>
  :global(body) {
    background: #040404;
  }
</style>
