<script lang="ts">
  const roadmapItems = [
    'Contracts signed instantly, like DocuSign',
    'Enterprise-grade AI video generation',
    'Influencer outreach automation',
    'Advanced audience analytics',
    'Cross-platform campaign scheduling'
  ];
</script>

<section class="coming-soon">
  <div class="container">
    <div class="content-wrapper">
      <div class="left-section">
        <div class="badge-pill">THE ROADMAP</div>
        <h2 class="section-title">The Future is Fast</h2>
        <p class="section-subtitle">
          We're building the next generation of marketing infrastructure. Here's a glimpse of what's on the horizon.
        </p>
      </div>

      <div class="right-section">
        <ul class="roadmap-list">
          {#each roadmapItems as item, i}
            <li class="roadmap-item" style="--delay: {i * 0.1}s">
              <div class="check-icon">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
                  <polyline points="20 6 9 17 4 12"/>
                </svg>
              </div>
              <span>{item}</span>
            </li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</section>

<style>
  .coming-soon {
    padding: 8rem 2rem;
    background: linear-gradient(180deg, #040404 0%, #0a0a0a 50%, #040404 100%);
    position: relative;
    overflow: hidden;
  }

  .coming-soon::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 800px;
    height: 800px;
    background: radial-gradient(circle, rgba(124, 58, 237, 0.1) 0%, transparent 70%);
    pointer-events: none;
  }

  .container {
    max-width: 1200px;
    margin: 0 auto;
    position: relative;
    z-index: 2;
  }

  .content-wrapper {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6rem;
    align-items: center;
  }

  .left-section {
    text-align: left;
  }

  .badge-pill {
    display: inline-block;
    padding: 0.5rem 1.5rem;
    background: transparent;
    border: none;
    color: var(--accent);
    font-size: 0.85rem;
    font-weight: 700;
    margin-bottom: 2rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
  }

  .section-title {
    font-size: clamp(2.5rem, 5vw, 4.5rem);
    font-weight: 900;
    letter-spacing: -0.03em;
    margin-bottom: 1.5rem;
    line-height: 1.1;
  }

  .section-subtitle {
    font-size: clamp(1rem, 2vw, 1.2rem);
    color: rgba(255, 255, 255, 0.6);
    line-height: 1.7;
  }

  .right-section {
    position: relative;
  }

  .roadmap-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 1.75rem;
  }

  .roadmap-item {
    display: flex;
    align-items: center;
    gap: 1.25rem;
    font-size: 1.25rem;
    color: rgba(255, 255, 255, 0.9);
    animation: fadeInRight 0.8s ease forwards;
    animation-delay: var(--delay);
    opacity: 0;
  }

  @keyframes fadeInRight {
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }

  .roadmap-item {
    transform: translateX(30px);
  }

  .check-icon {
    flex-shrink: 0;
    width: 36px;
    height: 36px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: rgba(124, 58, 237, 0.15);
    border: 2px solid var(--accent);
    border-radius: 50%;
    color: var(--accent);
    transition: all 0.3s ease;
  }

  .roadmap-item:hover .check-icon {
    background: var(--accent);
    color: #ffffff;
    transform: scale(1.1);
  }

  @media (max-width: 1024px) {
    .content-wrapper {
      grid-template-columns: 1fr;
      gap: 4rem;
    }

    .left-section {
      text-align: center;
    }
  }

  @media (max-width: 768px) {
    .coming-soon {
      padding: 5rem 1.5rem;
    }

    .content-wrapper {
      gap: 3rem;
    }

    .roadmap-item {
      font-size: 1.1rem;
    }

    .check-icon {
      width: 32px;
      height: 32px;
    }

    .check-icon svg {
      width: 20px;
      height: 20px;
    }
  }
</style>
