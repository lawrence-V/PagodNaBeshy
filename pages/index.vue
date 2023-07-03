<template>
  <v-row
    no-gutters
    class="fill-height pa-4"
    justify="center"
    align-content="center"
  >
    <v-col cols="12" lg="6" md="6" v-if="$vuetify.breakpoint.mdAndUp">
      <v-img :src="Logo"></v-img>
    </v-col>
    <v-col cols="12" lg="6">
      <v-col cols="12">
        <v-textarea
          color="rgba(220, 220, 220, 0.9)"
          v-model="inputText"
          solo
          name="input-7-4"
          label="Solo textarea"
        ></v-textarea>
        <v-btn depressed color="primary" @click="generateText">Generate</v-btn>
      </v-col>
      <v-col cols="12">
        <v-textarea
          readonly
          solo
          name="output-7-4"
          label="Generated Text"
          v-model="generatedText"
        ></v-textarea>
        <v-btn depressed color="primary" @click="copyText">Copy Text</v-btn>
      </v-col>
      <v-col cols="12" lg="6" md="6" v-if="$vuetify.breakpoint.smAndDown">
        <v-img :src="Logo"></v-img>
      </v-col>
      <v-dialog v-model="showModal" max-width="400">
        <v-card>
          <v-card-title class="headline">Text Copied</v-card-title>
          <v-card-text> The generated text has been copied </v-card-text>
          <v-card-actions>
            <v-btn color="primary" text @click="showModal = false">Close</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      Logo: require("@/static/beshy.png"),
      inputText: "",
      generatedText: "",
      showModal: false,
    };
  },
  methods: {
    generateText() {
      const words = this.inputText.split(" ");
      const generatedText = words.join(" 🤸🏻 ");
      this.generatedText = generatedText;
    },
    copyText() {
      const textarea = document.createElement("textarea");
      textarea.value = this.generatedText;
      document.body.appendChild(textarea);
      textarea.select();
      document.execCommand("copy");
      document.body.removeChild(textarea);

      this.showModal = true; // Show the modal
    },
  },
};
</script>

<style>
</style>
