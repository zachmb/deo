<script lang="ts">
  const features = [
    {
      title: 'Slack & Discord Integration',
      description: 'Streamline workflows with our intelligent bot in your favorite communication tools.',
      icon: 'slack',
      color: '#7C3AED'
    },
    {
      title: 'Creator Dashboards',
      description: 'Personalized analytics and performance tracking to empower your creators.',
      icon: 'chart',
      color: '#A78BFA'
    },
    {
      title: 'AI Video & Caption Generation',
      description: 'Create platform-optimized content in seconds, from viral videos to engaging captions.',
      icon: 'video',
      color: '#7C3AED'
    },
    {
      title: 'Post Tracking & Niche Insights',
      description: 'Analyze post performance and discover key insights to dominate your niche.',
      icon: 'search',
      color: '#A78BFA'
    },
    {
      title: 'Automated Onboarding',
      description: 'Generate onboarding docs and auto-sign contracts to scale your creator program effortlessly.',
      icon: 'document',
      color: '#7C3AED'
    },
    {
      title: 'Gamified Growth Tools',
      description: 'Boost team motivation and campaign performance with built-in gamification and incentives.',
      icon: 'trophy',
      color: '#A78BFA'
    }
  ];
</script>

<section id="features" class="features">
  <div class="container">
    <div class="section-header">
      <h2 class="section-title">
        A Fully-Integrated OS
      </h2>
      <p class="section-subtitle">
        Everything you need to build, manage, and scale your social media empire.
      </p>
    </div>

    <div class="features-boxy-grid">
      {#each features as feature, i}
        <div
          class="boxy-card"
          style="--delay: {i * 0.1}s; --color: {feature.color}"
        >
          <div class="card-inner">
            <div class="card-icon" style="color: {feature.color}">
              {#if feature.icon === 'slack'}
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M14.5 10c-.83 0-1.5-.67-1.5-1.5v-5c0-.83.67-1.5 1.5-1.5s1.5.67 1.5 1.5v5c0 .83-.67 1.5-1.5 1.5z"/>
                  <path d="M20.5 10H19V8.5c0-.83.67-1.5 1.5-1.5s1.5.67 1.5 1.5-.67 1.5-1.5 1.5z"/>
                  <path d="M9.5 14c.83 0 1.5.67 1.5 1.5v5c0 .83-.67 1.5-1.5 1.5S8 21.33 8 20.5v-5c0-.83.67-1.5 1.5-1.5z"/>
                  <path d="M3.5 14H5v1.5c0 .83-.67 1.5-1.5 1.5S2 16.33 2 15.5 2.67 14 3.5 14z"/>
                  <path d="M14 14.5c0-.83.67-1.5 1.5-1.5h5c.83 0 1.5.67 1.5 1.5S21.33 16 20.5 16h-5c-.83 0-1.5-.67-1.5-1.5z"/>
                  <path d="M15.5 19H14v1.5c0 .83.67 1.5 1.5 1.5s1.5-.67 1.5-1.5-.67-1.5-1.5-1.5z"/>
                  <path d="M10 9.5C10 8.67 9.33 8 8.5 8h-5C2.67 8 2 8.67 2 9.5S2.67 11 3.5 11h5c.83 0 1.5-.67 1.5-1.5z"/>
                  <path d="M8.5 5H10V3.5C10 2.67 9.33 2 8.5 2S7 2.67 7 3.5 7.67 5 8.5 5z"/>
                </svg>
              {:else if feature.icon === 'chart'}
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <line x1="12" y1="20" x2="12" y2="10"/>
                  <line x1="18" y1="20" x2="18" y2="4"/>
                  <line x1="6" y1="20" x2="6" y2="16"/>
                </svg>
              {:else if feature.icon === 'video'}
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <polygon points="23 7 16 12 23 17 23 7"/>
                  <rect x="1" y="5" width="15" height="14" rx="2" ry="2"/>
                </svg>
              {:else if feature.icon === 'search'}
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <circle cx="11" cy="11" r="8"/>
                  <line x1="21" y1="21" x2="16.65" y2="16.65"/>
                </svg>
              {:else if feature.icon === 'document'}
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/>
                  <polyline points="14 2 14 8 20 8"/>
                  <line x1="16" y1="13" x2="8" y2="13"/>
                  <line x1="16" y1="17" x2="8" y2="17"/>
                  <polyline points="10 9 9 9 8 9"/>
                </svg>
              {:else if feature.icon === 'trophy'}
                <svg width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/>
                  <path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/>
                  <path d="M4 22h16"/>
                  <path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/>
                  <path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/>
                  <path d="M18 2H6v7a6 6 0 0 0 12 0V2Z"/>
                </svg>
              {/if}
            </div>
            <h3 class="card-title">{feature.title}</h3>
            <p class="card-description">{feature.description}</p>
            <div class="card-accent"></div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .features {
    padding: 8rem 2rem;
    background: #040404;
    position: relative;
  }

  .features::before {
    content: '';
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 1px;
    height: 100%;
    background: linear-gradient(to bottom, transparent, rgba(124, 58, 237, 0.2), transparent);
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

  .gradient-text {
    background: linear-gradient(135deg, #A78BFA 0%, #7C3AED 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .section-subtitle {
    font-size: clamp(1rem, 2vw, 1.3rem);
    color: rgba(255, 255, 255, 0.6);
    max-width: 700px;
    margin: 0 auto;
  }

  .features-boxy-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
  }

  .boxy-card {
    position: relative;
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.1);
    padding: 2.5rem;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    animation: fadeInScale 0.8s ease forwards;
    animation-delay: var(--delay);
    opacity: 0;
    overflow: hidden;
  }

  @keyframes fadeInScale {
    to {
      opacity: 1;
      transform: scale(1);
    }
  }

  .boxy-card {
    transform: scale(0.95);
  }

  .boxy-card:hover {
    transform: scale(1.02);
    border-color: var(--color);
    background: rgba(255, 255, 255, 0.05);
  }

  .boxy-card:hover .card-accent {
    opacity: 1;
    transform: translateX(0);
  }

  .card-inner {
    position: relative;
    z-index: 2;
  }

  .card-icon {
    margin-bottom: 1.5rem;
    display: inline-block;
    transition: transform 0.3s ease;
  }

  .boxy-card:hover .card-icon {
    transform: scale(1.1);
  }

  .card-title {
    font-size: 1.4rem;
    font-weight: 700;
    margin-bottom: 1rem;
    line-height: 1.3;
  }

  .card-description {
    font-size: 1rem;
    color: rgba(255, 255, 255, 0.6);
    line-height: 1.7;
  }

  .card-accent {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 4px;
    background: linear-gradient(90deg, var(--color), transparent);
    opacity: 0;
    transform: translateX(-100%);
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  }

  @media (max-width: 768px) {
    .features {
      padding: 5rem 1.5rem;
    }

    .features-boxy-grid {
      grid-template-columns: 1fr;
      gap: 1.5rem;
    }

    .boxy-card {
      padding: 2rem;
    }
  }
</style>
