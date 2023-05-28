<template>
  <div class="banner">
  </div>
  <!-- Sign-up form start -->
  <form class="form">
    <h1 class="title">Stay updated!</h1>
    <p>
      Join 60,000+ product managers receiving monthly updates on:
    <ul class="list">
      <li class="list__item">Product discovery and building what matters</li>
      <li class="list__item">Measuring to ensure updates are a success</li>
      <li class="list__item">And much more!</li>
    </ul>
    </p>
    <div class="form__field">
      <label for="email" class="form__label">Email address</label>
      <input type="email" class="form__control" name="email" id="email" placeholder="email@company.com">
    </div>

    <button type="submit" class="btn btn-submit">Subscribe to monthly newsletter</button>
  </form>
  <!-- Sign-up form end -->
</template>
<script></script>
<style scoped>
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

.form__label,
.form__control {
  display: block;
  width: 100%;
}

.form__label {
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 0.8rem;
}

.form__control {
  border-radius: 8px;
  border: 1px solid var(--color-grey);
  padding: 1.6rem 2.4rem;
}

.form__control::placeholder {
  color: var(--color-dark-navy-50);
}

@media only screen and (width >=768px) {
  .banner {
    background: url('../assets/images/illustration-sign-up-desktop.svg') no-repeat center / cover;
  }
}
</style>