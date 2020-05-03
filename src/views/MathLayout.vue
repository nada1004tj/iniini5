<template>
  <v-app id="inspire">
    <!-- {!@@! Cmp Top -->
    <cmp-top-bar v-on:fnDrawerChange="fnDrawer"></cmp-top-bar>
    <!-- Cmp Top END}-->
    <!-- {!@@! Cmp LEFT MENU -->
    <cmp-left-menu
      :prop-drawer-value="drawer"
      v-on:fnChangeLayout="fnChangeLayout"
    ></cmp-left-menu>
    <!-- Cmp LEFT END}-->

    <v-content>
      <!-- {!@@! Cmp Contents -->
      <cmp-one-grade-plus v-if="pageGubun === 'onePlus'"></cmp-one-grade-plus>
      <cmp-one-grade-Minus
        v-else-if="pageGubun === 'oneMinus'"
      ></cmp-one-grade-Minus>
      <!-- Cmp Contents END}-->
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
  import CmpOneGradePlus from "@/components/contents/OneGradePlus";
  import CmpOneGradeMinus from "@/components/contents/OneGradeMinus";

  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: true,
      dialog: false,
      pageGubun: "oneMinus",
    }),
    components: {
      CmpTopBar,
      CmpLeftMenu,
      CmpDialog,
      CmpOneGradePlus,
      CmpOneGradeMinus,
    },
    methods: {
      fnDrawer: function() {
        this.drawer = !this.drawer;
      },
      fnChangeLayout: function(pageGubun) {
        this.pageGubun = pageGubun;
      },
    },
  };
</script>
