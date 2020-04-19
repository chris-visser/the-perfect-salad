<template>
  <div class="wrapper">

    <section class="main-content columns">
      <aside class="column is-2 section">
        <h1>The Random Salad Selector</h1>
        <p class="menu-label is-hidden-touch">
          Lazy fucks as we are.. Do you suck at selecting your meal? Here's a random Salad ingredient selector...
        </p>
      </aside>

      <div class="container column is-10">
        <nuxt />
      </div>
    </section>

    <footer class="footer">
      <div class="content has-text-centered">
        <p>
          <strong>The Salad Selector</strong> by <a href="https://thespider.netlify.app/">Chris Visser</a>.
        </p>
      </div>
    </footer>
  </div>
</template>

<style>
.footer {
  position: absolute;
  bottom: 0;
  width: 100%;
}
</style>
