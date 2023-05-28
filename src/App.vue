<script>

</script>

<template>
  <div class="container">
    <main class="main">
      <!-- <SignUpForm /> -->
      <Confirmation />
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
</style>
