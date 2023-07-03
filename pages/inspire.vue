<template>
  <v-row>
    <v-col class="text-center">
      <img
        :src="Logo"
        alt="Vuetify.js"
        class="mb-5"
        max-height="150"
        max-width="250"
      />
      <blockquote class="blockquote" style="color: black">
        &#8220;Para di kana mapagod mag lagay ng 🤸🏻 Pagod naba ang bessy ko
        &#8221;
        <footer>
          <small>
            <em>&mdash;Lawrence B Valdez</em>
          </small>
        </footer>
      </blockquote>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "InspirePage",
  data() {
    return {
      Logo: require("@/static/beshy.png"),
    };
  },
};
</script>
