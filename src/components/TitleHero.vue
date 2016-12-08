<template>
  <section class="box hero">
    <div class="hero-body">
      <div class="container">
        <h1 class="title">ToDo{{suffix}}</h1>
        <h2 class="subtitle">The ultimate ToDo App</h2>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  computed: {
    suffix() {
      const list = [
        'er',
        'ist',
        'ify',
        'lagoo',
        'om',
        'inizer',
      ];
      return list[Math.floor((Math.random() * list.length))];
    },
  },
};
</script>
