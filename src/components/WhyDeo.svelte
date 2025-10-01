<script lang="ts">
  const features = [
    {
      icon: 'bot',
      title: 'AI Slack Bot for Marketers',
      description: 'Instant insights, content generation, and team coordination right in your workspace.'
    },
    {
      icon: 'chart',
      title: 'Dashboards & Training OS',
      description: 'Crystal-clear analytics and onboarding tools that scale your team effortlessly.'
    },
    {
      icon: 'settings',
      title: 'Automated Contracts + Growth Tools',
      description: 'Sign deals instantly and accelerate your campaigns with intelligent automation.'
    }
  ];
</script>

<section class="why-deo">
  <div class="container">
    <div class="section-header">
      <h2 class="section-title">Why Deo?</h2>
      <p class="section-subtitle">
        One platform. Infinite possibilities. Built for the future of social media marketing.
      </p>
    </div>

    <div class="features-grid">
      {#each features as feature, i}
        <div class="feature-card" style="--delay: {i * 0.1}s">
          <div class="feature-icon">
            {#if feature.icon === 'bot'}
              <svg width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <rect x="3" y="11" width="18" height="10" rx="2"/>
                <circle cx="12" cy="5" r="2"/>
                <path d="M12 7v4"/>
                <line x1="8" y1="16" x2="8" y2="16"/>
                <line x1="16" y1="16" x2="16" y2="16"/>
              </svg>
            {:else if feature.icon === 'chart'}
              <svg width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <rect x="3" y="3" width="18" height="18" rx="2"/>
                <path d="M7 10h10"/>
                <path d="M7 14h7"/>
                <path d="M16 14h1"/>
              </svg>
            {:else if feature.icon === 'settings'}
              <svg width="64" height="64" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <circle cx="12" cy="12" r="3"/>
                <path d="M12 1v6m0 6v6m6-11h-6m-6 0H1m17.5 3.5l-4.5 4.5m0-9l4.5 4.5m-9 0L4.5 15.5m0-9l4.5 4.5"/>
              </svg>
            {/if}
          </div>
          <h3 class="feature-title">{feature.title}</h3>
          <p class="feature-description">{feature.description}</p>
          <div class="feature-glow"></div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .why-deo {
    padding: 8rem 2rem;
    position: relative;
    background: linear-gradient(180deg, #040404 0%, #0a0a0a 100%);
  }

  .container {
    max-width: 1400px;
    margin: 0 auto;
  }

  .section-header {
    text-align: center;
    margin-bottom: 5rem;
  }

  .section-title {
    font-size: clamp(2.5rem, 5vw, 4rem);
    font-weight: 900;
    letter-spacing: -0.03em;
    margin-bottom: 1.5rem;
  }

  .section-subtitle {
    font-size: clamp(1rem, 2vw, 1.3rem);
    color: rgba(255, 255, 255, 0.6);
    max-width: 700px;
    margin: 0 auto;
  }

  .features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 2.5rem;
  }

  .feature-card {
    position: relative;
    padding: 3rem;
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 24px;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    overflow: hidden;
    animation: fadeInUp 0.8s ease forwards;
    animation-delay: var(--delay);
    opacity: 0;
  }

  @keyframes fadeInUp {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .feature-card {
    transform: translateY(30px);
  }

  .feature-card:hover {
    transform: translateY(-8px);
    border-color: rgba(124, 58, 237, 0.3);
    background: rgba(255, 255, 255, 0.05);
  }

  .feature-card:hover .feature-glow {
    opacity: 1;
  }

  .feature-glow {
    position: absolute;
    inset: -100px;
    background: radial-gradient(circle at center, var(--accent-glow) 0%, transparent 70%);
    opacity: 0;
    transition: opacity 0.4s ease;
    pointer-events: none;
  }

  .feature-icon {
    margin-bottom: 1.5rem;
    display: inline-block;
    animation: float 3s ease-in-out infinite;
    color: var(--accent);
  }

  .feature-icon svg {
    width: 64px;
    height: 64px;
  }

  @keyframes float {
    0%, 100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-10px);
    }
  }

  .feature-title {
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: 1rem;
    line-height: 1.3;
  }

  .feature-description {
    font-size: 1.05rem;
    color: rgba(255, 255, 255, 0.6);
    line-height: 1.7;
  }

  @media (max-width: 768px) {
    .why-deo {
      padding: 5rem 1.5rem;
    }

    .features-grid {
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .feature-card {
      padding: 2rem;
    }
  }
</style>
