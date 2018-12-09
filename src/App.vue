<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <br>
        <button
          @click="selectedComponent = 'appBlue', blueCmp()"
          class="btn btn-primary"
        >Load Blue Template</button>
        <button
          @click="selectedComponent = 'appGreen', greenCmp()"
          class="btn btn-success"
        >Load Green Template</button>
        <button
          @click="selectedComponent = 'appRed', redCmp()"
          class="btn btn-danger"
        >Load Red Template</button>
        <hr>
        <component :is="selectedComponent">{{selectedData}}</component>
        <!-- <app-blue>
          <p>This is blue content</p>
        </app-blue>
        <app-green>
          <p>This is green content</p>
        </app-green>
        <app-red>
          <p>This is red content</p>
        </app-red>-->
      </div>
    </div>
  </div>
</template>

<script>
import Blue from "./components/Blue.vue";
import Green from "./components/Green.vue";
import Red from "./components/Red.vue";

export default {
  data() {
    return {
      selectedComponent: "",
      selectedData: ""
    };
  },

  methods: {
    blueCmp() {
      this.selectedComponent = "app-blue";
      this.selectedData = "This is blue!";
    },
    greenCmp() {
      this.selectedComponent = "app-green";
      this.selectedData = "This is Green!";
    },
    redCmp() {
      this.selectedComponent = "app-red";
      this.selectedData = "This is Red!";
    }
  },

  components: {
    appBlue: Blue,
    appGreen: Green,
    appRed: Red
  }
};
</script>

<style>
</style>
