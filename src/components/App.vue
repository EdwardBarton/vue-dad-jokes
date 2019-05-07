<template>
    <main class="text-center">
      <button class="btn btn-primary my-5" @click="getDadJoke">New Joke</button>
      <h1>{{ joke }}</h1>
    </main>
</template>

<script>
export default {
  data() {
    return {
      joke: ""
    };
  },
  methods: {
    async getDadJoke() {
      const resp = await fetch("https://icanhazdadjoke.com/", {
        headers: {
          Accept: "application/json"
        }
      });
      const json = await resp.json();

      this.joke = json.joke;
    }
  }
};
</script>

<style scoped>
</style>