<script setup lang="ts"></script>

<template>
  <section class="hero-section">
    <img src="/helpero.svg" alt="Helpero Logo" class="logo" />
    <h1 class="main-heading">Spájame ľudí s úlohami.</h1>
    <p class="sub-heading">
      Pomáhame nájsť alebo ponúknuť flexibilné práce v okolí.
    </p>
    <div class="actions">
      <a href="#wishlist" class="btn btn-primary">Pridajte sa k nám</a>
      <a href="#about" class="btn btn-secondary">Ďalšie informácie</a>
    </div>
  </section>
</template>

<style scoped lang="scss">
.hero-section {
  padding-top: 80px;
  height: 90dvh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: var(--white);
  font-family: sans-serif;

  .logo {
    margin-bottom: 3rem;
    width: 300px;
  }

  .actions {
    margin-top: 3rem;
    display: flex;
    gap: 1rem;

    .btn {
      font-size: 1.2rem;
      text-align: center;
    }
  }
}

@media (max-width: 768px) {
  .hero-section {
    .main-heading {
      font-size: 2.5rem;
    }

    .sub-heading {
      font-size: 1.5rem;
    }
  }
}

@media (max-width: 525px) {
  .hero-section {
    .main-heading {
      font-size: 2rem;
    }

    .sub-heading {
      font-size: 1.25rem;
    }

    .actions {
      flex-direction: column;
      width: 80%;
    }
  }
}
</style>
