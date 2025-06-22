<script setup lang="ts">
import { ref } from "vue";
import { API_URL } from "../constants";

const email = ref("");
const role = ref("");
const errorMessage = ref({
  email: "",
  role: "",
  general: "",
  success: "",
});
const loading = ref(false);

const handleSubmit = () => {
  errorMessage.value = {
    email: "",
    role: "",
    general: "",
    success: "",
  };

  if (!email.value) {
    errorMessage.value.email = "Vyplňte váš email";
  }

  if (!role.value) {
    errorMessage.value.role = "Vyberte si rolu";
  }

  if (!email.value || !role.value) {
    errorMessage.value.general = "Vyplňte všetky polia";
    return;
  }

  loading.value = true;

  const submitButton = document.querySelector(
    "button[type='submit']"
  ) as HTMLButtonElement;
  submitButton.disabled = true;

  fetch(`${API_URL}/wishlist`, {
    method: "POST",
    body: JSON.stringify({ email: email.value, role: role.value }),
  })
    .then((res) => res.json())
    .then((data) => {
      if (data.success) {
        errorMessage.value.success =
          "Boli ste pridaný na čakaciu listinu. Ďakujeme!";
        email.value = "";
        role.value = "";
        submitButton.disabled = false;
      }
    })
    .catch((err) => {
      console.error(err);
      errorMessage.value.general =
        "Nepodarilo sa pridať na čakaciu listinu. Skúste to znova.";
      submitButton.disabled = false;
    })
    .finally(() => {
      loading.value = false;
    });
};
</script>

<template>
  <section id="wishlist">
    <h2 class="main-heading">Pridajte sa na čakaciu listinu.</h2>
    <p class="sub-heading">
      Budeme vás informovať o všetkých novinkách a aktivitách.
    </p>
    <form class="wishlist-form" @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="email">Váš email</label>
        <input
          type="email"
          placeholder="Váš email"
          required
          v-model="email"
          :class="{ error: errorMessage.email }"
        />
        <p class="error-message" v-if="errorMessage.email">
          {{ errorMessage.email }}
        </p>
      </div>
      <div class="form-group">
        <label for="role">Mám záujem</label>
        <div class="radio-container">
          <div class="radio-group">
            <input
              type="radio"
              name="role"
              value="seeker"
              id="seeker"
              v-model="role"
              :class="{ error: errorMessage.role }"
            />
            <label for="seeker">Hľadať prácu</label>
          </div>
          <div class="radio-group">
            <input
              type="radio"
              name="role"
              value="provider"
              id="provider"
              v-model="role"
              :class="{ error: errorMessage.role }"
            />
            <label for="provider">Ponúknuť prácu</label>
          </div>
        </div>
        <p class="error-message" v-if="errorMessage.role">
          {{ errorMessage.role }}
        </p>
      </div>
      <p
        :class="{
          'error-message': errorMessage.general,
          'success-message': errorMessage.success,
        }"
        class="text-center"
        v-if="errorMessage.general || errorMessage.success"
      >
        {{ errorMessage.general || errorMessage.success }}
      </p>
      <button type="submit" class="btn btn-primary">
        <span v-if="loading">
          <div class="loading-spinner"></div>
          Pridávam...
        </span>
        <span v-else>Pridajte sa na čakaciu listinu</span>
      </button>
    </form>
  </section>
</template>

<style scoped lang="scss">
#wishlist {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 80dvh;
  border-top: 3px solid var(--gray-light);
  border-bottom: 3px solid var(--gray-light);

  .main-heading {
    font-size: 2rem;
  }

  .sub-heading {
    font-size: 1.5rem;
    margin-bottom: 2rem;
  }

  .wishlist-form {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    width: 400px;
    max-width: 100%;

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 0.5rem;

      label {
        font-weight: 500;
      }

      input[type="email"] {
        padding: 0.75rem 1rem;
        border-radius: 12px;
        border: 1px solid var(--gray-light);
        background-color: var(--gray-light);
        font-size: 1rem;
        transition: border-color 0.2s;

        &:focus {
          outline: none;
          border: 1px solid var(--black);
        }
      }
    }

    .radio-container {
      display: flex;
      gap: 1rem;
    }

    .radio-group {
      flex: 1;
      position: relative;

      input[type="radio"] {
        appearance: none;
        position: absolute;
        width: 100%;
        height: 100%;
        cursor: pointer;
        margin: 0;
        z-index: 1;
        border-radius: 12px;

        &:focus {
          outline: none;
          border: 1px solid var(--black);
        }

        &:checked + label {
          background-color: #cfcfcf;
        }
      }

      label {
        display: block;
        text-align: center;
        padding: 0.75rem 1rem;
        border-radius: 12px;
        transition: all 0.2s;
        background-color: var(--gray-light);
        color: var(--black);
      }
    }

    .btn {
      padding: 1rem;
      border-radius: 12px;

      &[type="submit"] {
        span {
          display: flex;
          align-items: center;
          justify-content: center;
          gap: 0.5rem;
        }
      }
    }

    .error-message {
      color: var(--danger);
      font-size: 0.875rem;

      &.success-message {
        color: var(--success);
      }
    }
  }
}

@media (max-width: 768px) {
  #wishlist {
    .main-heading {
      text-align: left;
      width: 100%;
    }

    .sub-heading {
      text-align: left;
      width: 100%;
    }

    .wishlist-form {
      width: 100%;
    }
  }
}

@media (max-width: 425px) {
  #wishlist {
    .radio-container {
      flex-direction: column;
    }
  }
}
</style>
