<script>

</script>

<template>
  <div class="container">
    <main class="main">
      <SignUpForm v-if="!showConfirmation" @submit="handleSubmit" />
      <Confirmation v-else @dismiss="handleDismiss" :email="enteredEmail" />
    </main>
    <footer class="attribution">
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>.
      Coded by <a href="https://github.com/deejayjay">DeeJayJay</a>.
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
    handleSubmit(enteredEmail) {
      this.enteredEmail = enteredEmail;
      this.showConfirmation = true;
    },
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
  background-color: var(--color-white);
  transition: background-color 0.3s ease-in-out;
}

@media only screen and (width >= 1024px) {
  .main {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .attribution {
    background-color: var(--color-charcoal-grey);
  }
}
</style>
