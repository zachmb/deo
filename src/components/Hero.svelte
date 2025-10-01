<script lang="ts">
  import { onMount } from 'svelte';

  let mounted = false;

  onMount(() => {
    mounted = true;
  });

  function scrollToBeta() {
    const betaSection = document.getElementById('beta');
    if (betaSection) {
      betaSection.scrollIntoView({ 
        behavior: 'smooth',
        block: 'start'
      });
    }
  }
</script>

<section class="hero">
  <div class="animated-bg">
    <div class="grid-overlay"></div>
    <div class="particles">
      {#each Array(30) as _, i}
        <div class="particle" style="--delay: {i * 0.2}s; --duration: {15 + (i % 10)}s;"></div>
      {/each}
    </div>
  </div>

  <div class="hero-content" class:mounted>
    <h1 class="hero-title">
      The AI OS for<br/>
      <span class="gradient-text">Social Media Marketing</span>
    </h1>

    <p class="hero-subtitle">
      Unify your creators, campaigns, and growth into one intelligent platform.
    </p>

    <button class="cta-button" on:click={scrollToBeta}>
      <span>Get Early Access</span>
      <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
        <path d="M7.5 15L12.5 10L7.5 5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </button>
  </div>
</section>

<style>
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
    padding: 8rem 2rem 4rem;
  }

  .animated-bg {
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse at center, rgba(124, 58, 237, 0.1) 0%, transparent 70%);
  }

  .grid-overlay {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
    background-size: 80px 80px;
    animation: gridMove 20s linear infinite;
  }

  @keyframes gridMove {
    0% { transform: translate(0, 0); }
    100% { transform: translate(80px, 80px); }
  }

  .particles {
    position: absolute;
    inset: 0;
  }

  .particle {
    position: absolute;
    width: 3px;
    height: 3px;
    background: var(--accent);
    border-radius: 50%;
    animation: float var(--duration) ease-in-out infinite;
    animation-delay: var(--delay);
    opacity: 0;
    left: calc(var(--delay) * 10);
    box-shadow: 0 0 10px var(--accent-glow);
  }

  @keyframes float {
    0%, 100% {
      transform: translate(0, 0) scale(0);
      opacity: 0;
    }
    10% {
      opacity: 1;
      transform: scale(1);
    }
    90% {
      opacity: 1;
    }
    100% {
      transform: translate(calc(100vw - var(--delay) * 50), calc(100vh - var(--delay) * 30)) scale(0);
      opacity: 0;
    }
  }

  .hero-content {
    position: relative;
    z-index: 2;
    text-align: center;
    max-width: 1100px;
    opacity: 0;
    transform: translateY(30px);
    transition: all 1s cubic-bezier(0.4, 0, 0.2, 1);
  }

  .hero-content.mounted {
    opacity: 1;
    transform: translateY(0);
  }

  .hero-title {
    font-size: clamp(3rem, 8vw, 7rem);
    font-weight: 900;
    line-height: 1.1;
    letter-spacing: -0.04em;
    margin-bottom: 1.5rem;
  }

  .gradient-text {
    background: linear-gradient(135deg, #A78BFA 0%, #7C3AED 50%, #A78BFA 100%);
    background-size: 200% 200%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: gradientShift 3s ease infinite;
  }

  @keyframes gradientShift {
    0%, 100% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
  }

  .hero-subtitle {
    font-size: clamp(1.1rem, 2vw, 1.5rem);
    color: rgba(255, 255, 255, 0.7);
    margin-bottom: 3rem;
    font-weight: 400;
    max-width: 700px;
    margin-left: auto;
    margin-right: auto;
  }

  .cta-button {
    display: inline-flex;
    align-items: center;
    gap: 0.75rem;
    padding: 1.25rem 3rem;
    font-size: 1.1rem;
    font-weight: 700;
    background: linear-gradient(135deg, #A78BFA 0%, #7C3AED 100%);
    color: #FFFFFF;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    box-shadow: 0 20px 60px rgba(124, 58, 237, 0.3);
  }

  .cta-button:hover {
    transform: translateY(-4px);
    box-shadow: 0 30px 80px rgba(124, 58, 237, 0.5);
  }

  .cta-button svg {
    transition: transform 0.3s ease;
  }

  .cta-button:hover svg {
    transform: translateX(4px);
  }

  @media (max-width: 768px) {
    .hero {
      padding: 6rem 1.5rem 3rem;
    }
  }
</style>
