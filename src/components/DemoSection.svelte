<script lang="ts">
  import { onMount } from 'svelte';

  let currentSlide = 0;
  const slides = [
    {
      title: 'Unified Creator Dashboard',
      description: 'Track all your creators, campaigns, and content in one beautiful interface.',
      mockup: 'dashboard'
    },
    {
      title: 'AI Slack Bot Assistant',
      description: 'Get instant answers, generate captions, and approve content without leaving Slack.',
      mockup: 'slack'
    },
    {
      title: 'Real-time Analytics',
      description: 'Predictive insights that tell you what to do next, not just what happened.',
      mockup: 'analytics'
    }
  ];

  let interval: number;

  onMount(() => {
    interval = setInterval(() => {
      currentSlide = (currentSlide + 1) % slides.length;
    }, 5000);

    return () => clearInterval(interval);
  });

  function goToSlide(index: number) {
    currentSlide = index;
    clearInterval(interval);
    interval = setInterval(() => {
      currentSlide = (currentSlide + 1) % slides.length;
    }, 5000);
  }
</script>

<section id="demo" class="demo-section">
  <div class="container">
    <div class="section-header">
      <h2 class="section-title">Experience <span class="gradient-text">Deo</span></h2>
      <p class="section-subtitle">
        A glimpse into the future of social media marketing operations.
      </p>
    </div>

    <div class="demo-carousel">
      <div class="carousel-content">
        {#each slides as slide, i}
          <div class="slide" class:active={currentSlide === i}>
            <div class="slide-text">
              <h3 class="slide-title">{slide.title}</h3>
              <p class="slide-description">{slide.description}</p>
            </div>
            <div class="slide-mockup mockup-{slide.mockup}">
              {#if slide.mockup === 'dashboard'}
                <div class="mockup-content">
                  <div class="mockup-header">
                    <div class="header-tabs">
                      <div class="tab active">Overview</div>
                      <div class="tab">Creators</div>
                      <div class="tab">Campaigns</div>
                    </div>
                  </div>
                  <div class="mockup-stats">
                    <div class="stat-card">
                      <div class="stat-label">Total Reach</div>
                      <div class="stat-value">4.2M</div>
                    </div>
                    <div class="stat-card">
                      <div class="stat-label">Active Creators</div>
                      <div class="stat-value">127</div>
                    </div>
                    <div class="stat-card">
                      <div class="stat-label">Engagement</div>
                      <div class="stat-value">8.4%</div>
                    </div>
                  </div>
                </div>
              {:else if slide.mockup === 'slack'}
                <div class="mockup-content slack-mockup">
                  <div class="slack-message bot">
                    <div class="message-avatar">
                      <img src="/deo.png" alt="Deo Bot" style="width: 100%; height: 100%; object-fit: cover; border-radius: 50%;" />
                    </div>
                    <div class="message-content">
                      <div class="message-header">Deo Bot</div>
                      <div class="message-text">Generated 3 caption variations for your review</div>
                    </div>
                  </div>
                  <div class="slack-message user">
                    <div class="message-avatar">👤</div>
                    <div class="message-content">
                      <div class="message-header">You</div>
                      <div class="message-text">Approve option 2</div>
                    </div>
                  </div>
                </div>
              {:else if slide.mockup === 'analytics'}
                <div class="mockup-content analytics-mockup">
                  <div class="chart-container">
                    {#each Array(12) as _, i}
                      <div class="chart-bar" style="height: {30 + Math.random() * 60}%"></div>
                    {/each}
                  </div>
                </div>
              {/if}
            </div>
          </div>
        {/each}
      </div>

      <div class="carousel-indicators">
        {#each slides as _, i}
          <button
            class="indicator"
            class:active={currentSlide === i}
            on:click={() => goToSlide(i)}
          ></button>
        {/each}
      </div>
    </div>
  </div>
</section>

<style>
  .demo-section {
    padding: 8rem 2rem;
    background: #040404;
    position: relative;
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

  .demo-carousel {
    position: relative;
    max-width: 1200px;
    margin: 0 auto;
  }

  .carousel-content {
    position: relative;
    min-height: 600px;
  }

  .slide {
    position: absolute;
    inset: 0;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: center;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.8s ease;
  }

  .slide.active {
    opacity: 1;
    pointer-events: auto;
  }

  .slide-text {
    text-align: left;
  }

  .slide-title {
    font-size: 2.5rem;
    font-weight: 800;
    margin-bottom: 1.5rem;
    line-height: 1.2;
  }

  .slide-description {
    font-size: 1.2rem;
    color: rgba(255, 255, 255, 0.6);
    line-height: 1.7;
  }

  .slide-mockup {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 24px;
    padding: 2rem;
    min-height: 400px;
    backdrop-filter: blur(20px);
  }

  .mockup-header {
    margin-bottom: 2rem;
  }

  .header-tabs {
    display: flex;
    gap: 1rem;
  }

  .tab {
    padding: 0.75rem 1.5rem;
    background: rgba(255, 255, 255, 0.05);
    border-radius: 8px;
    font-size: 0.9rem;
    color: rgba(255, 255, 255, 0.5);
  }

  .tab.active {
    background: rgba(124, 58, 237, 0.2);
    color: var(--accent);
  }

  .mockup-stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }

  .stat-card {
    padding: 1.5rem;
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 12px;
  }

  .stat-label {
    font-size: 0.85rem;
    color: rgba(255, 255, 255, 0.5);
    margin-bottom: 0.5rem;
  }

  .stat-value {
    font-size: 2.5rem;
    font-weight: 800;
    color: var(--accent);
  }

  .slack-mockup {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }

  .slack-message {
    display: flex;
    gap: 1rem;
    align-items: flex-start;
  }

  .message-avatar {
    width: 40px;
    height: 40px;
    border-radius: 8px;
    background: rgba(255, 255, 255, 0.1);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
  }

  .message-content {
    flex: 1;
  }

  .message-header {
    font-weight: 700;
    font-size: 0.9rem;
    margin-bottom: 0.25rem;
  }

  .message-text {
    background: rgba(255, 255, 255, 0.05);
    padding: 0.75rem 1rem;
    border-radius: 8px;
    font-size: 0.95rem;
  }

  .analytics-mockup {
    display: flex;
    align-items: flex-end;
    justify-content: center;
    min-height: 350px;
  }

  .chart-container {
    display: flex;
    align-items: flex-end;
    gap: 1rem;
    width: 100%;
    height: 300px;
  }

  .chart-bar {
    flex: 1;
    background: linear-gradient(to top, #A78BFA, #7C3AED);
    border-radius: 8px 8px 0 0;
    animation: growBar 1s ease-out;
  }

  @keyframes growBar {
    from { height: 0; }
  }

  .carousel-indicators {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin-top: 3rem;
  }

  .indicator {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.2);
    border: none;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .indicator.active {
    background: var(--accent);
    transform: scale(1.3);
  }

  @media (max-width: 1024px) {
    .slide {
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .carousel-content {
      min-height: 800px;
    }

    .slide-text {
      text-align: center;
    }
  }

  @media (max-width: 768px) {
    .demo-section {
      padding: 5rem 1.5rem;
    }

    .mockup-stats {
      grid-template-columns: 1fr;
    }
  }
</style>
