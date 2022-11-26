<template>
  <v-app>
    <div id="#app">
      <v-container>
        <v-layout v-for="index in rows" row wrap>
          <v-col style="background-color: cyan;">{{index}}</v-col>
          <v-col style="background-color: red;">{{index}}</v-col>
          <v-col style="background-color: blue;">{{index}}</v-col>
          <v-col style="background-color: purple;">{{index}}</v-col>
          <v-col style="background-color: pink;">{{index}}</v-col>
          <v-col style="background-color: yellow;">{{index}}</v-col>
          <v-col style="background-color: aqua;">{{index}}</v-col>
          <v-col style="background-color: brown;">{{index}}</v-col>
          <v-col style="background-color: violet;">{{index}}</v-col>
          <v-col style="background-color: white;">{{index}}</v-col>
          <v-col style="background-color: palevioletred;">{{index}}</v-col>
          <v-col style="background-color: gold;">{{index}}</v-col>
          <v-col style="background-color: green;">{{index}}</v-col>
          <v-col style="background-color: grey;">{{index}}</v-col>
          <v-col style="background-color: salmon;">{{index}}</v-col>
          <v-col style="background-color: rebeccapurple;">{{index}}</v-col>
          <v-col style="background-color: olive;">{{index}}</v-col>
          <v-col style="background-color: navy;">{{index}}</v-col>
          <v-col style="background-color: slateblue;">{{index}}</v-col>
          <v-col style="background-color: maroon;">{{index}}</v-col>
        </v-layout>
      </v-container>
      <br/>
      <p>Counter</p>
      <p>{{ counter }}</p>
      <v-btn rounded color="success" @click="btnClickPlus()"
        ><v-icon>mdi-plus</v-icon></v-btn
      >
      <v-btn rounded color="error" @click="btnClickMinus()"
        ><v-icon>mdi-minus</v-icon></v-btn
      >
      <v-container>
        <v-layout row wrap>
          <v-col cols="4" class="blue" v-show="counter % 2 === 0"></v-col>
          <v-col cols="4" class="yellow" v-show="counter % 2 !== 0"></v-col>
        </v-layout>
      </v-container>
      <p v-for="index in counter">Привет! Как дела?</p>
    </div>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    color: "",
    rows: 10,
    colm: 20,
    counter: 0,
  }),
  methods: {
    btnClickPlus() {
      this.counter += 1;
    },
    btnClickMinus() {
      this.counter -= 1;
    },
    randomColor() {
      const hexvalues = [
        "0",
        "1",
        "2",
        "3",
        "4",
        "5",
        "6",
        "7",
        "8",
        "9",
        "a",
        "b",
        "c",
        "d",
        "e",
        "f",
      ];
      let hex = "#";
      for (let i = 0; i < 6; i++) {
        let randomIndex = Math.floor(hexvalues.length * Math.random());
        let randomValue = hexvalues[randomIndex];
        hex += randomValue;
      }
      console.log(hex);
      this.color = hex;
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothig: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
.yellow {
  background-color: yellow;
  margin-left: 800px;
}
.blue {
  background-color: blue;
}
</style>
