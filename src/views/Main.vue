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
          <v-col cols="10">
            <v-card>
              <v-card-text>
                <v-row>
                  <v-col cols="12" md="6">
                    <span>Scheme</span>
                    <v-switch
                      v-model="$vuetify.theme.dark"
                      primary
                      label="Dark"
                    />
                  </v-col>
                  <v-col cols="12" md="6">
                    <span>Drawer</span>
                    <v-radio-group v-model="primaryDrawer.type" column>
                      <v-radio
                        v-for="drawer in drawers"
                        :key="drawer"
                        :label="drawer"
                        :value="drawer.toLowerCase()"
                        primary
                      />
                    </v-radio-group>
                    <v-switch
                      v-model="primaryDrawer.clipped"
                      label="Clipped"
                      primary
                    />
                    <v-switch
                      v-model="primaryDrawer.floating"
                      label="Floating"
                      primary
                    />
                    <v-switch
                      v-model="primaryDrawer.mini"
                      label="Mini"
                      primary
                    />
                  </v-col>
                </v-row>
              </v-card-text>
              <v-card-actions>
                <v-spacer />
                <v-btn text>Cancel</v-btn>
                <v-btn text color="primary">Submit</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
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
      primaryDrawer: {
        model: null,
        type: "default (no property)",
        clipped: false,
        floating: false,
        mini: false,
      },
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
