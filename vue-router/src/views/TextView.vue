<template>
  <div>
    <input type="text" v-model="name" />
    <h1>Hello, {{ name }}</h1>
    <h2 v-text="name"></h2>
    <h3 v-html="htmlContent"></h3>
  </div>
  <button @click="addCount">+</button>
  <span>&emsp;{{ count }}&emsp;</span>
  <button @click="count--">-</button><br /><br />
  <button @click="changeLink" :div="{ active: ifBtnActive }">change</button
  ><br /><br />
  <a :href="link" :title="linkName">{{ linkName }}</a
  ><br /><br />
  <div @click="ToggleActive" class="box" :class="{ active: ifActive }"></div>
</template>

<script>
export default {
  name: "TextView",
  data() {
    return {
      name: "Eddy",
      htmlContent: "Hello <span>World</span>",
      count: 0,
      linkName: "GitHub",
      link: "https://github.com",
      ifActive: false,
      ifBtnActive: false,
    };
  },
  methods: {
    addCount() {
      this.count++;
    },
    changeLink() {
      if ((this.ifBtnActive = !this.ifBtnActive)) {
        this.linkName = "Facebook";
        this.link = "http://www.facebook.com";
      } else if (this.ifBtnActive != !this.ifBtnActive) {
        this.linkName = "GitHub";
        this.link = "https://github.com/";
      }
    },
    ToggleActive() {
      this.ifActive = !this.ifActive;
    },
  },
};
</script>

<style>
a {
  text-decoration: none;
}
button, .box{
  cursor: pointer;
}
.box {
  margin: 0 auto;
  width: 150px;
  height: 150px;
  background: pink;
  transition: 0.5s;
}
.box.active {
  background: red;
}
</style>