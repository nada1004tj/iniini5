<template>
  <v-container class="fill-height" fluid>
    <v-row align="center" justify="center">
      <v-tooltip right>
        <span>Source</span>
      </v-tooltip>
      <v-tooltip right>
        <template v-slot:activator="{ on }">
          <v-btn
            icon
            large
            href="https://codepen.io/johnjleider/pen/MNYLdL"
            target="_blank"
            v-on="on"
          >
            <slot>빼기3</slot>
          </v-btn>
        </template>
        <span>Codepen</span>
      </v-tooltip>
    </v-row>
  </v-container>
</template>
<script>
  export default {};
</script>
<style scoped></style>
