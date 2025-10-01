<script lang="ts">
  import { onMount } from 'svelte';

  let scrolled = false;

  onMount(() => {
    const handleScroll = () => {
      scrolled = window.scrollY > 50;
    };

    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<nav class:scrolled>
  <div class="nav-container">
    <div class="logo">
      <span class="logo-text"><span class="logo-gradient">Deo</span><span class="logo-white">.so</span></span>
    </div>

    <div class="nav-links">
      <a href="#features">Features</a>
      <a href="#demo">Demo</a>
    </div>
  </div>
</nav>

<style>
  nav {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    padding: 1.5rem 0;
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  }

  nav.scrolled {
    background: rgba(4, 4, 4, 0.8);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    padding: 1rem 0;
  }

  .nav-container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo-text {
    font-size: 1.5rem;
    font-weight: 800;
    letter-spacing: -0.02em;
  }

  .logo-gradient {
    background: linear-gradient(135deg, #A78BFA 0%, #7C3AED 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .logo-white {
    color: #FFFFFF;
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
    align-items: center;
  }

  .nav-links a {
    font-size: 0.95rem;
    font-weight: 500;
    color: rgba(255, 255, 255, 0.7);
    transition: color 0.3s ease;
    position: relative;
  }

  .nav-links a:hover {
    color: #FFFFFF;
  }

  .nav-links a::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--accent);
    transition: width 0.3s ease;
  }

  .nav-links a:hover::after {
    width: 100%;
  }

  @media (max-width: 768px) {
    .nav-container {
      padding: 0 1.5rem;
    }

    .nav-links {
      gap: 1.5rem;
    }
  }
</style>
