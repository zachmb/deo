<script lang="ts">
  let email = '';
  let submitted = false;

  function handleSubmit(e: Event) {
    e.preventDefault();
    submitted = true;
    setTimeout(() => {
      submitted = false;
      email = '';
    }, 3000);
  }
</script>

<section id="beta" class="final-cta">
  <div class="cta-glow"></div>

  <div class="container">
    <div class="cta-content">
      <h2 class="cta-title">
        Reserve Your Spot<br/>
        in the <span class="gradient-text">Beta</span>
      </h2>

      <p class="cta-subtitle">
        Build the future of UGC with Deo. Limited early access spots available.
      </p>

      <form class="cta-form" on:submit={handleSubmit}>
        <input
          type="email"
          placeholder="Enter your email"
          class="email-input"
          bind:value={email}
          required
          disabled={submitted}
        />
        <button type="submit" class="submit-button" disabled={submitted}>
          {submitted ? 'Submitted!' : 'Get Early Access'}
        </button>
      </form>

      <div class="cta-features">
        <div class="feature-item">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path d="M16.6667 5L7.50004 14.1667L3.33337 10" stroke="#7C3AED" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <span>Priority onboarding</span>
        </div>
        <div class="feature-item">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path d="M16.6667 5L7.50004 14.1667L3.33337 10" stroke="#7C3AED" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <span>Exclusive feature access</span>
        </div>
        <div class="feature-item">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
            <path d="M16.6667 5L7.50004 14.1667L3.33337 10" stroke="#7C3AED" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <span>Direct support from our team</span>
        </div>
      </div>
    </div>
  </div>

  <footer class="footer">
    <div class="footer-content">
      <div class="footer-logo">
        <span class="logo-gradient">Deo</span><span class="logo-white">.so</span>
      </div>
      <div class="footer-text">The AI OS for Social Media Marketing</div>
      <div class="footer-copy">2025 Deo. All rights reserved.</div>
    </div>
  </footer>
</section>

<style>
  .final-cta {
    padding: 10rem 2rem 0;
    background: #040404;
    position: relative;
    overflow: hidden;
  }

  .cta-glow {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 1000px;
    height: 1000px;
    background: radial-gradient(circle, rgba(124, 58, 237, 0.15) 0%, transparent 70%);
    pointer-events: none;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    position: relative;
    z-index: 2;
  }

  .cta-content {
    text-align: center;
    padding: 4rem;
    background: rgba(255, 255, 255, 0.02);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 32px;
    backdrop-filter: blur(20px);
  }

  .cta-title {
    font-size: clamp(2.5rem, 5vw, 4.5rem);
    font-weight: 900;
    letter-spacing: -0.03em;
    line-height: 1.1;
    margin-bottom: 1.5rem;
  }

  .gradient-text {
    background: linear-gradient(135deg, #A78BFA 0%, #7C3AED 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .cta-subtitle {
    font-size: clamp(1.1rem, 2vw, 1.4rem);
    color: rgba(255, 255, 255, 0.6);
    margin-bottom: 3rem;
    line-height: 1.6;
  }

  .cta-form {
    display: flex;
    gap: 1rem;
    max-width: 600px;
    margin: 0 auto 3rem;
  }

  .email-input {
    flex: 1;
    padding: 1.25rem 1.75rem;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.2);
    border-radius: 12px;
    color: white;
    font-size: 1rem;
    font-family: inherit;
    transition: all 0.3s ease;
  }

  .email-input:focus {
    outline: none;
    border-color: var(--accent);
    background: rgba(255, 255, 255, 0.08);
  }

  .email-input::placeholder {
    color: rgba(255, 255, 255, 0.4);
  }

  .submit-button {
    padding: 1.25rem 2.5rem;
    background: linear-gradient(135deg, #A78BFA 0%, #7C3AED 100%);
    color: #FFFFFF;
    border: none;
    border-radius: 12px;
    font-size: 1rem;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    white-space: nowrap;
  }

  .submit-button:hover:not(:disabled) {
    transform: translateY(-2px);
    box-shadow: 0 20px 60px rgba(124, 58, 237, 0.4);
  }

  .submit-button:disabled {
    opacity: 0.7;
    cursor: not-allowed;
  }

  .cta-features {
    display: flex;
    flex-wrap: wrap;
    gap: 2rem;
    justify-content: center;
  }

  .feature-item {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    color: rgba(255, 255, 255, 0.7);
    font-size: 0.95rem;
  }

  .footer {
    margin-top: 8rem;
    padding: 3rem 2rem;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
  }

  .footer-content {
    max-width: 1400px;
    margin: 0 auto;
    text-align: center;
  }

  .footer-logo {
    font-size: 1.5rem;
    font-weight: 800;
    margin-bottom: 0.5rem;
  }

  .footer-logo .logo-gradient {
    background: linear-gradient(135deg, #A78BFA 0%, #7C3AED 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .footer-logo .logo-white {
    color: #FFFFFF;
  }

  .footer-text {
    color: rgba(255, 255, 255, 0.5);
    font-size: 0.95rem;
    margin-bottom: 1rem;
  }

  .footer-copy {
    color: rgba(255, 255, 255, 0.3);
    font-size: 0.85rem;
  }

  @media (max-width: 768px) {
    .final-cta {
      padding: 6rem 1.5rem 0;
    }

    .cta-content {
      padding: 2.5rem 1.5rem;
    }

    .cta-form {
      flex-direction: column;
    }

    .cta-features {
      flex-direction: column;
      align-items: center;
      gap: 1rem;
    }

    .footer {
      margin-top: 5rem;
    }
  }
</style>
