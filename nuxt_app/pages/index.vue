<template>
  <section class="container">
    <h1 class="title">{{ title }}</h1>
    <p class="subtitle">{{ $store.state.message }}</p>
    <hr>
    <div class="link" 
    @click="$store.commit('doit')">
      <button @click.stop="$store.commit('reset')">reset</button>
      <p>total: {{ $store.state.counter }}</p>
    </div>
  </section>
</template>

<script>
  export default {
    data: function() {
      return {
        title: 'Hello',
        message: 'this is message.'
      };
    }
  };
</script>

<style>
.container {
  padding: 0 20px;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

button {
  width: 100px;
  height: 30px;
  background: black;
  color: white;
  margin: 10px 0;
  font-weight: bold;
}
</style>
