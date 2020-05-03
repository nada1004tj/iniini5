<template>
  <v-app id="inspire">
    <!-- {!@@! Cmp Top -->
    <cmp-top-bar v-on:fnDrawerChange="fnDrawer"></cmp-top-bar>
    <!-- Cmp Top END}-->
    <!-- {!@@! Cmp LEFT MENU -->
    <cmp-left-menu :prop-drawer-value="drawer"></cmp-left-menu>
    <!-- Cmp LEFT END}-->
    <v-content>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-tooltip right>
            <template v-slot:activator="{ on }">
              <v-btn :href="source" icon large target="_blank" v-on="on">
                <v-icon large>mdi-code-tags</v-icon>
              </v-btn>
            </template>
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
                <slot>빼기</slot>
              </v-btn>
            </template>
            <span>Codepen</span>
          </v-tooltip>
        </v-row>
      </v-container>
    </v-content>
    <v-btn bottom color="pink" dark fab fixed right @click="dialog = !dialog">
      <v-icon>mdi-plus</v-icon>
    </v-btn>
    <!-- {!@@! Cmp Dialog -->
    <cmp-dialog></cmp-dialog>
    <!-- Cmp Dialog END}-->
  </v-app>
</template>

<script>
  import CmpTopBar from "@/components/TopBar";
  import CmpLeftMenu from "@/components/LeftMenu";
  import CmpDialog from "@/components/Dialog";

  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: true,
      dialog: false,
    }),
    components: {
      CmpTopBar,
      CmpLeftMenu,
      CmpDialog,
    },
    methods: {
      fnDrawer: function() {
        this.drawer = !this.drawer;
      },
    },
  };
</script>
