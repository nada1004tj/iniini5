<template>
  <v-container fluid>
    <v-layout>
      <v-flex xs24>
        <v-card>
          <v-layout column>
            <div class="dv3">
              <v-flex xs10>
                <v-tabs :class="`d-flex align-start mb-6`">
                  <v-tab v-for="i in 3" :key="i" :href="'#tab-' + i">Item {{ i }}</v-tab>
                </v-tabs>
              </v-flex>
            </div>
            <div class="dv2">
              <v-flex :class="`d-flex align-start mb-0`">
                <p class="p" :class="`headline`">{{ title.mainTitle }}</p>
              </v-flex>
            </div>
            <div class="dv3"></div>
            <div class="dv2">
              <v-flex>
                <div class="dv3">
                  <v-card-actions :class="`d-flex align-start mb-4`">
                    <v-btn flat color="orange">{{ title.btnAnswer }}</v-btn>
                    <v-btn flat color="orange">{{ title.print }}</v-btn>
                  </v-card-actions>
                  <div class="page">
                    <v-container fluid>
                      <v-row no-gutters>
                        <v-col cols="12" sm="8" md="7">
                          <v-card
                            class="pa-4"
                            outlined
                            tile
                            justify-lg-center
                          >{{printContents.headerTitle}}</v-card>
                        </v-col>
                        <v-col cols="3" md="5">
                          <v-card class="pa-4" outlined tile>{{printContents.headerScore}}</v-card>
                        </v-col>
                      </v-row>
                      <v-row no-gutters :class="`d-flex align-start mb-6`">
                        <v-col cols="3" md="5"></v-col>
                      </v-row>
                      <div>
                        <v-row no-gutters :class="`d-flex align-start mb-6`">
                          <v-col>
                            <v-card
                              v-for="i in 5"
                              v-bind:key="i"
                              height="100%"
                              outlined
                              tile
                              justify-lg-centers
                            >
                              <div class="dv4">{{ i }}) 1+1=</div>
                            </v-card>
                          </v-col>
                          <v-col cols="3" md="6">
                            <v-card
                              v-for="i in 5"
                              v-bind:key="i"
                              height="100%"
                              outlined
                              tile
                              justify-lg-centers
                            >
                              <div class="dv4">{{ i }}) 1+1=</div>
                            </v-card>
                          </v-col>
                        </v-row>
                      </div>
                    </v-container>
                  </div>
                </div>
              </v-flex>
            </div>
          </v-layout>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      card_text:
        "Lorem ipsum dolor sit amet, brute iriure accusata ne mea. Eos suavitate referrentur ad, te duo agam libris qualisque, utroque quaestio accommodare no qui. Et percipit laboramus usu, no invidunt verterem nominati mel. Dolorem ancillae an mei, ut putant invenire splendide mel, ea nec propriae adipisci. Ignota salutandi accusamus in sed, et per malis fuisset, qui id ludus appareat.",
      title: {
        mainTitle: "더하기",
        subTitle: "1학년 수학",
        btnAnswer: "정답보기",
        print: "출력하기"
      },
      printContents: {
        headerTitle: "1학년더하기",
        headerScore: "점수 : ",
        headerScoreValue: "점"
      }
    };
  }
};
</script>
<style scoped>
.resultContainer {
  height: 350px;
}

.item {
  min-height: 50px;
  min-width: 80px;
  margin: 10px;
}

.dv {
  text-align: left;
  border: 4px;
}

.dv2 {
  border: 5px;
}

.dv3 {
  border: 5px;
}

.dv4 {
  border: 5px;
  height: 5cm;
  margin-left: 5px;
  margin-top: 10px;
}

.p {
  margin-left: 10px;
}

.page {
  width: 21cm;
  min-height: 29.7cm;
  padding: 6px;
  margin: 1px auto;
  border-radius: 5px;
  background: white;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
}
</style>
