<template>
  <!-- Success message start -->
  <div class="wrapper">
    <section class="content">
      <div class="content__text">
        <h1 class="title">Thanks for subscribing!</h1>
        <p>
          A confirmation email has been sent to <strong class="strong">ash@loremcompany.com</strong>.
          Please open it and click the button inside to confirm your subscription.
        </p>
      </div>
      <button type="button" class="btn">Dismiss message</button>
    </section>
  </div>
  <!-- Success message end -->
</template>

<style scoped>
.wrapper {
  padding: 4rem 2.4rem;
  height: 100%;
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
</style>