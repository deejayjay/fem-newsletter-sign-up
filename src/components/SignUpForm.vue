<template>
  <div class="wrapper">
    <div class="banner">
    </div>
    <!-- Sign-up form start -->
    <form class="form" @submit.prevent="handleSubmit" :novalidate="true">
      <h1 class="title">Stay updated!</h1>
      <p>
        Join 60,000+ product managers receiving monthly updates on:
      </p>
      <ul class="list">
        <li class="list__item">Product discovery and building what matters</li>
        <li class="list__item">Measuring to ensure updates are a success</li>
        <li class="list__item">And much more!</li>
      </ul>      
      <div class="form__field">
        <div class="form__label-container">
          <label for="email" class="form__label">Email address</label>
          <p class="error" v-if="!isValidEmail" id="email-error" role="alert">{{ errorMessage }}</p>
        </div>
        <input type="email" class="form__control" :class="{invalid: !isValidEmail}" name="email" id="email" placeholder="email@company.com" v-model="email" aria-describedby="email-error">
      </div>
  
      <button type="submit" class="btn btn-submit">Subscribe to monthly newsletter</button>
    </form>
    <!-- Sign-up form end -->
  </div>
</template>

<script>
export default {
  name: 'SignUpForm',
  emits: ['submit'],
  data() {
    return {
      email: '',
      errorMessage: '',
      isValidEmail: true
    };
  },
  methods: {
    // When the form is submitted, check if the email is valid.
    // If form is valid, emit the submit event and pass the email as payload
    handleSubmit() {
      this.validateEmail(this.email);
      if (this.isValidEmail) {
        this.$emit('submit', this.email);
      }      
    },
    validateEmail(userInput) {
      // Check if userInput is not an empty string or whitespace
      if (userInput.trim() === '') {
        this.isValidEmail = false;
        this.errorMessage = 'Email address is required';        
        return;
      }

      // Check if userInput is a valid email address
      const emailRegex = /^[\w.-]+@[a-zA-Z]+\.[a-zA-Z]{2,3}$/;
      if (!emailRegex.test(userInput)) {
        this.isValidEmail = false;
        this.errorMessage = 'Oops, wrong format';
        return;
      }

      // Email is valid
      this.isValidEmail = true;
      this.errorMessage = '';
    }
  }
}
</script>
<style scoped>
.wrapper {
  background-color: var(--color-white);
  height: 100%;
}
.banner {
  background: url('../assets/images/illustration-sign-up-mobile.svg') no-repeat center / cover;
  height: 28.4rem;
  border-radius: 0 0 16px 16px;
  overflow: hidden;
}

.form {
  padding: 4rem 2.4rem;
}

.list {
  margin-top: 2.4rem;
}

.list__item {
  position: relative;
  padding-left: 3.2rem;
  margin-bottom: 1rem;
}

.list__item::before {
  content: url("../assets/icons/icon-list.svg");
  width: 21px;
  height: 21px;
  position: absolute;
  top: 0;
  left: 0;
}

.form__field {
  margin: 3rem 0 2.4rem;
}

.form__label-container {
  display: flex;
  justify-content: space-between;
  font-size: 1.2rem;  
  font-weight: 700;
  margin-bottom: 0.8rem;
}

.error {
  color: var(--color-primary);
}

.form__control {
  display: block;
  width: 100%;
  border-radius: 8px;
  border: 1px solid var(--color-grey);
  outline: 1px solid transparent;
  background-color: transparent;
  padding: 1.6rem 2.4rem;
  transition: border-color 0.3s, outline 0.3s, background-color 0.3s;
}

.form__control:focus-visible {
  border-color: var(--color-dark-navy);
  outline-color: var(--color-dark-navy);
}

.form__control::placeholder {
  color: var(--color-dark-navy-50);
}

.form__control.invalid {
  border-color: var(--color-primary);
  color: var(--color-primary);
  background-color: var(--color-primary-15);
}

@media only screen and (width >= 1024px) {
  .banner {
    background: url('../assets/images/illustration-sign-up-desktop.svg') no-repeat center / cover;
  }

  .wrapper {
    width: 100%;
    max-width: 92.8rem;
    height: initial;
    border-radius: 36px;
    overflow: hidden;
    display: grid;
    grid-template-columns: 1fr 40rem;
    gap: 6.4rem;
    grid-template-areas: 'left right';
    padding: 2.4rem;
  }

  .banner {
    height: 100%;
    grid-area: right;
  }

  .form {
    padding: 7.4rem 0 7.3rem 4rem;  
    grid-area: left;
  }

  .form__field {
    margin-top: 4rem;
  }
}
</style>