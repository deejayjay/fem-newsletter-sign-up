<template>
  <!-- Success message start -->
  <div class="wrapper">
    <section class="content">
      <div class="content__text">
        <h1 class="title">Thanks for subscribing!</h1>
        <p class="content__message">
          A confirmation email has been sent to <strong class="strong">{{ email }}</strong>.
          Please open it and click the button inside to confirm your subscription.
        </p>
      </div>
      <button type="button" class="btn" @click="handleDismissClick">Dismiss message</button>
    </section>
  </div>
  <!-- Success message end -->
</template>

<script>
export default {
  name: 'Confirmation',
  emits: ['dismiss'],
  props: {
    email: {
      type: String,
      required: true
    }
  },
  methods: {
    // Emit dismiss event when user clicks on the button so that 
    // the SignUpForm component can be displayed again
    handleDismissClick() {
      this.$emit('dismiss');
    }
  }
}
</script>

<style scoped>
.wrapper {
  padding: 14.9rem 2.4rem 4rem;
  height: 100%;
  background-color: var(--color-white);
}

.content {
  display: flex;
  flex-direction: column;
  height: 100%;
  padding-top: 10.9rem;
  position: relative;
}

.content::before {
  content: url("../assets/icons/icon-success.svg");
  width: 64px;
  height: 64px;
  position: absolute;
  top: 0;
  left: 0;
}

.content__text {
  flex: 1;
}

.strong {
  font-weight: 700;
}

@media only screen and (width >= 1024px) {
  .wrapper {
    width: 100%;
    max-width: 50.4rem;
    height: initial;
    border-radius: 3.6rem;
    padding: 4.8rem 6.4rem 6.4rem;
  }

  .content {
    padding-top: 10.4rem;
  }

  .content__message {
    margin-bottom: 4rem;
  }
}
</style>