<script setup lang="ts"></script>

<template>
  <nav class="navbar">
    <div class="logo">
      <img src="/helpero.svg" alt="Helpero" class="logo-img" />
    </div>
    <div class="nav-links">
      <a href="#about">O nás</a>
      <a href="#how-it-works">Ako to funguje</a>
      <a href="#services">Služby</a>
    </div>
    <a href="#wishlist" class="btn btn-primary">Pridajt sa k nám</a>
  </nav>
</template>

<style lang="scss" scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5rem var(--side-padding);
  background-color: white;
  border-bottom-left-radius: 15px;
  border-bottom-right-radius: 15px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  height: 80px;

  .logo {
    display: flex;
    align-items: center;
    .logo-img {
      width: 200px;
    }
  }

  .nav-links {
    display: flex;
    gap: 2.5rem;
  }

  .nav-links a {
    text-decoration: none;
    color: #6b7280;
    font-size: 1rem;
  }
}

@media (max-width: 768px) {
  .navbar {
    .nav-links {
      display: none;
    }
  }
}

@media (max-width: 480px) {
  .navbar {
    padding: 1rem var(--side-padding);
    .logo {
      .logo-img {
        width: 150px;
      }
    }

    .cta-btn {
      padding: 0.5rem 1rem;
    }
  }
}
</style>
