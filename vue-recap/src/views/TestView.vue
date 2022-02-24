<template>
  <div class="wrapper">
    <input type="text" v-model="name" />
    <h1>Hello, {{ name }}!</h1>
    <h1 v-text="name"></h1>
    <div v-html="htmlContent"></div>
    <hr />
    <div>
      <!-- click, mouseenter... -->
      <!-- <button v-on:click="count++">add</button> |  -->
      <button v-on:click="addCount">add</button>
    </div>
    click: <span>{{ count }}</span>
    <hr />
    <div>
      <button @click="changeLink">change</button>
    </div>
    <!-- <a href="https://www.google.com">Google1</a> |  -->
    <a v-bind:href="link" :title="linkName">{{ linkName }}</a>
    <hr />
    <!-- <div class="box" :class="ifActive"></div> -->
    <div @click="toggleActive" class="box" :class="{ active: ifActive }"></div>
  </div>
</template>

<script>
// .text(), .html()
export default {
  name: "TestView",
  data() {
    return {
      name: "Joe",
      htmlContent: "test <span>content</span>",
      count: 0,
      linkName: "Google",
      link: "https://www.google.com",
      // ifActive: "active",
      ifActive: false,
    };
  },
  methods: {
    addCount() {
      // console.log("click");
      this.count++;
    },
    changeLink() {
      this.linkName = "facebook";
      this.link = "https://www.facebook.com";
    },
    toggleActive() {
      this.ifActive = !this.ifActive;
    },
  },
};
</script>

<style>
.box {
  width: 150px;
  height: 150px;
  background-color: pink;
  transition: 0.5s;
}

.box.active {
  background-color: red;
}
</style>