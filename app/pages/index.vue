<template>
  <div>
    <header>
      <div>
        <h1>Roboaeste</h1>
      </div>
    </header>
    <section id="input-section">
      <div>
        <Input v-model="prompt" placeholder="Insert your prompt..." style="width: 500px" />
      </div>
      <div>
        <Button type="success" @click="genImage">Generated</Button>
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        prompt: ""
      }
    },
    methods: {
      genImage() {
        console.log(this.prompt);
      }
    }
  }
</script>

<style scoped>
  * {
    text-align: center;
  }
</style>
