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
  import { Configuration, OpenAIApi } from 'openai';
  const configuration = new Configuration({ apiKey: "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" })
  const openai = new OpenAIApi(configuration);
  export default {
    data() {
      return {
        prompt: "",
        apiKey: "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",
        openAI: {},
        response: {}
      }
    },
    methods: {
      async genImage() {
        const response = await openai.createImage({
          prompt: this.prompt,
          n: 1,
          size: "1024x1024"
        })

        console.log(`Response: ${response}`);
      }
    }
  }
</script>

<style scoped>
  * {
    text-align: center;
  }
</style>
