<template>
  <div>
    <v-navigation-drawer
      v-model="darwerValue"
      :clipped="$vuetify.breakpoint.lgAndUp"
      app
    >
      <v-list dense>
        <template v-for="item in items">
          <v-row v-if="item.heading" :key="item.heading" align="center">
            <v-col cols="6">
              <v-subheader v-if="item.heading">{{ item.heading }}</v-subheader>
            </v-col>
            <v-col cols="6" class="text-center">
              <a href="#!" class="body-2 black--text">EDIT</a>
            </v-col>
          </v-row>
          <v-list-group
            v-else-if="item.children"
            :key="item.text"
            v-model="item.model"
            :prepend-icon="item.model ? item.icon : item['icon-alt']"
            append-icon
          >
            <template v-slot:activator>
              <v-list-item-content>
                <v-list-item-title>{{ item.text }}</v-list-item-title>
              </v-list-item-content>
            </template>
            <v-list-item v-for="(child, i) in item.children" :key="i" link>
              <v-list-item-action v-if="child.icon">
                <v-icon>{{ child.icon }}</v-icon>
              </v-list-item-action>
              <v-list-item-content>
                <v-list-item-title @click.stop="fnChangeLayout(child.symbol)">{{
                  child.text
                }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-group>
          <v-list-item v-else :key="item.text" link>
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{ item.text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </template>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
  export default {
    props: {
      propDrawerValue: {
        type: Boolean,
        required: false,
      },
    },
    data: () => ({
      //darwerValue: true,
      items: [
        /* { heading: "111" }, 관리자 모드*/
        { icon: "mdi-history", text: "조회시간" },
        { icon: "mdi-contacts", text: "나의학습진도" },
        { icon: "mdi-content-copy", text: "수업시간" },
        /*
      {
        icon: "mdi-chevron-up",
        "icon-alt": "mdi-chevron-down",
        text: "Labels",
        model: true,
        children: [{ icon: "mdi-plus", text: "Create label" }]
      },*/
        {
          icon: "mdi-chevron-up",
          "icon-alt": "mdi-chevron-down",
          text: "1학년수학",
          model: false,
          children: [
            {
              icon: "mdi-pencil-plus-outline",
              text: "더하기",
              href: "/oneGrade/OneGradePlus",
              symbol: "onePlus",
            },
            {
              icon: "mdi-pencil-minus-outline",
              text: "빼기",
              href: "/oneGrade/OneGradeMinus",
              symbol: "oneMinus",
            },
          ],
        },
        {
          icon: "mdi-chevron-up",
          "icon-alt": "mdi-chevron-down",
          text: "2학년수학",
          model: false,
          children: [
            { text: "Import" },
            { text: "Export" },
            { text: "Print" },
            { text: "Undo changes" },
            { text: "Other contacts" },
          ],
        },
        {
          icon: "mdi-chevron-up",
          "icon-alt": "mdi-chevron-down",
          text: "3학년수학",
          model: false,
          children: [
            { text: "Import" },
            { text: "Export" },
            { text: "Print" },
            { text: "Undo changes" },
            { text: "Other contacts" },
          ],
        },
        {
          icon: "mdi-chevron-up",
          "icon-alt": "mdi-chevron-down",
          text: "4학년수학",
          model: false,
          children: [
            { text: "Import" },
            { text: "Export" },
            { text: "Print" },
            { text: "Undo changes" },
            { text: "Other contacts" },
          ],
        },
        {
          icon: "mdi-chevron-up",
          "icon-alt": "mdi-chevron-down",
          text: "5학년수학",
          model: false,
          children: [
            { icon: "plus-square", text: "Import" },
            { text: "Export" },
            { text: "Print" },
            { text: "Undo changes" },
            { text: "Other contacts" },
          ],
        },
        {
          icon: "mdi-chevron-up",
          "icon-alt": "mdi-chevron-down",
          text: "6학년수학",
          model: false,
          children: [
            { text: "Import" },
            { text: "Export" },
            { text: "Print" },
            { text: "Undo changes" },
            { text: "Other contacts" },
          ],
        },
        { icon: "mdi-help-circle", text: "Help" },
        { icon: "mdi-cellphone-link", text: "쉬는시간" },
        { icon: "mdi-keyboard", text: "즐거운하교길" },
      ],
    }),
    computed: {
      darwerValue: {
        get: function() {
          return this.propDrawerValue;
        },
        // setter
        set: function() {},
      },
    },
    methods: {
      fnChangeLayout: function(symbol) {
        console.log("-------------" + symbol);
        this.$emit("fnChangeLayout", symbol);
      },
    },
  };
</script>

<style></style>
