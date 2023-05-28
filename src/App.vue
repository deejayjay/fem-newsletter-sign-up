<script>

</script>

<template>
  <div class="container">
    <main class="main">
      <SignUpForm v-if="!showConfirmation" @submit="handleSubmit" />
      <Confirmation v-else @dismiss="handleDismiss" :email="enteredEmail" />
    </main>
    <footer class="attribution">
      Challenge by 
      <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">
        Frontend Mentor <i class="bi bi-box-arrow-up-right"></i>
      </a>.
      Coded by 
      <a href="https://github.com/deejayjay">
        DeeJayJay <i class="bi bi-box-arrow-up-right"></i>
      </a>.
    </footer>
  </div>
</template>

<script>
import SignUpForm from './components/SignUpForm.vue';
import Confirmation from './components/Confirmation.vue';

export default {
  name: 'App',
  components: {
    SignUpForm,
    Confirmation
  },
  data() {
    return {
      showConfirmation: false,
      enteredEmail: ''
    };
  },
  methods: {
    // When the SignUpForm is submitted with a valid email, show the Confirmation component
    handleSubmit(enteredEmail) {
      this.enteredEmail = enteredEmail;
      this.showConfirmation = true;
    },
    // When the Confirmation page is dismissed, show the SignUpForm
    handleDismiss() {
      this.showConfirmation = false;
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  height: 100%;
}

.main {
  flex: 1;  
}

.attribution {
  font-size: 11px;
  text-align: center;
  color: hsl(228, 45%, 44%);
  background-color: var(--color-white);
  transition: background-color 0.3s ease-in-out;
  padding: 1rem;
}

.attribution a {
  color: hsl(228, 45%, 44%);
  text-decoration: underline hsl(228, 45%, 44%);
  transition: text-decoration-color 0.25s ease-in-out;
}

.attribution a:hover {
  text-decoration-color: transparent;
}

@media only screen and (width >= 1024px) {
  .main {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .attribution {
    color: var(--color-white);
    background-color: var(--color-charcoal-grey);
  }

  .attribution a {
    color: var(--color-white);
    text-decoration-color: var(--color-white);
  }
}
</style>
