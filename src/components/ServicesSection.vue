<script setup lang="ts"></script>

<template>
  <section id="services" class="services-section">
    <div class="features-one">
      <div class="feature">
        <div class="icon-placeholder">
          <svg width="60" height="60" viewBox="0 0 100 100">
            <rect x="20" y="20" width="60" height="60" rx="5" fill="#fff" />
          </svg>
        </div>
        <h3>Flexibilné a lokálne</h3>
        <p>
          Vyberte si alebo zverejnite úlohy vo vašom okolí pre lepšie
          zosúladenie práce a súkromia.
        </p>
      </div>
      <div class="feature">
        <div class="icon-placeholder">
          <svg width="60" height="60" viewBox="0 0 100 100">
            <circle cx="50" cy="50" r="30" fill="#fff" />
          </svg>
        </div>
        <h3>Bezpečné a zabezpečené</h3>
        <p>Overené profily a bezpečné pripojenia vám zaručia pokoj.</p>
      </div>
      <div class="feature">
        <div class="icon-placeholder">
          <svg width="60" height="60" viewBox="0 0 100 100">
            <polygon points="50,20 85,80 15,80" fill="#fff" />
          </svg>
        </div>
        <h3>Jednoduchá komunikácia</h3>
        <p>Chatujte bez problémov s ostatnými – žiadne skryté poplatky.</p>
      </div>
    </div>
    <div class="features-two">
      <div class="feature-small">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon>
        </svg>
        <h4>Žiadne skryté poplatky</h4>
      </div>
      <div class="feature-small">
        <svg width="24" height="24" viewBox="0 0 24 24">
          <path
            d="M12 2 L14.5 9.5 L22 12 L14.5 14.5 L12 22 L9.5 14.5 L2 12 L9.5 9.5 Z"
            fill="currentColor"
          />
        </svg>
        <h4>Transparentný proces</h4>
      </div>
      <div class="feature-small">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        >
          <path
            d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"
          ></path>
        </svg>
        <h4>Responzívna podpora</h4>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.services-section {
  padding: 6rem var(--side-padding);
  background-color: var(--white);
  text-align: center;
}

.features-one {
  display: flex;
  justify-content: space-around;
  gap: 2rem;
  margin-bottom: 6rem;
}

.feature {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;

  h3 {
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--black);
  }

  p {
    color: var(--gray);
    max-width: 300px;
    line-height: 1.6;
  }
}

.icon-placeholder {
  width: 120px;
  height: 120px;
  background-color: var(--gray-light);
  border-radius: 20px;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.features-two {
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.feature-small {
  display: flex;
  align-items: center;
  gap: 1rem;
  color: var(--gray);

  svg {
    width: 28px;
    height: 28px;
    color: var(--black);
  }

  h4 {
    font-size: 1.1rem;
    font-weight: 600;
  }
}

@media (max-width: 768px) {
  .about-section {
    padding: 4rem var(--side-padding);
  }
  .features-one {
    flex-direction: column;
    align-items: center;
    gap: 4rem;
    margin-bottom: 4rem;
  }
  .features-two {
    flex-direction: column;
    gap: 2rem;
    align-items: flex-start;
  }
}
</style>
