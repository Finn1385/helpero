<script setup lang="ts"></script>

<template>
  <footer class="footer">
    <div class="logo">
      <img src="/helpero.svg" alt="Helpero logo" />
    </div>
    <div class="links">
      <div class="column">
        <h3 class="title">Contact</h3>
        <ul class="list">
          <li><a href="mailto:info@helpero.sk">info@helpero.sk</a></li>
        </ul>
      </div>
      <div class="column">
        <h3 class="title">Sociálne média</h3>
        <ul class="list">
          <li><a href="#">Facebook</a></li>
          <li><a href="#">Instagram</a></li>
          <li><a href="#">LinkedIn</a></li>
        </ul>
      </div>
      <div class="column">
        <h3 class="title">Právne informácie</h3>
        <ul class="list">
          <li><a href="#">Podmienky používania</a></li>
          <li><a href="#">Ochrana osobných údajov</a></li>
          <li><a href="#">Cookies</a></li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  padding: 4rem var(--side-padding);
  background-color: var(--white);

  .logo {
    img {
      width: 100px;
      opacity: 0.5;
    }
  }

  .links {
    display: flex;
    gap: 4rem;
  }

  .column {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .title {
    font-size: 1rem;
    font-weight: 600;
    color: var(--black);
    margin-bottom: 0.5rem;
  }

  .list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;

    li a {
      color: var(--gray);
      text-decoration: none;
      font-size: 1rem;
      transition: color 0.2s;

      &:hover {
        color: var(--black);
      }
    }
  }
}

@media (max-width: 768px) {
  .footer {
    flex-direction: column;
    align-items: flex-start;
    gap: 3rem;
  }

  .links {
    flex-direction: column;
    gap: 2rem;
  }
}
</style>
