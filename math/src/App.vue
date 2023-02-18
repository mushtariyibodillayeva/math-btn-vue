<template>
  <div id="list-demo">
    <div class="flex">
      <img src="./components/think.gif" alt="think" />
      <h1>Mathematical examples:</h1>
    </div>
    <div class="math-card">
      <button @click="add" id="add">Add</button>
      <button @click="remove" id="remove">Remove</button>
      <transition-group name="list" teg="ul">
        <li v-for="item in items" :key="item.id" class="list-item">
          Item: {{ item * 7 }} - {{ item }} =
        </li>
      </transition-group>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      items: [1, 2, 3],
      nextNum: 10,
    };
  },
  methods: {
    randomItem() {
      return Math.floor(Math.random() * this.items.length);
    },
    add() {
      this.items.splice(this.randomItem(), 0, this.nextNum++);
    },
    remove() {
      this.items.splice(this.randomItem(), 1);
    },
  },
};
</script>
<style>
* {
  padding: 0;
  margin: 0;
}
body {
  background: url(components/back.jpg);
  font-family: cursive;
  height: 100vh;
}

.flex img {
  width: 200px;
  height: 200px;
  margin-right: 100px;
}
.flex {
  display: flex;
  align-items: center;
  justify-content: center;
}
.math-card {
  margin-left: 500px;
}
button {
  cursor: pointer;
  background: transparent;
  border: 1.3px solid #fff;
  width: 200px;
  height: 50px;
  color: aliceblue;
  font-size: 22px;
  border-radius: 15px;
  font-family: inherit;
  margin: 30px 0 30px 0;
}
#add {
  margin-right: 5px;
}
#add:hover {
  background-color: greenyellow;
}
#remove:hover {
  background-color: crimson;
}
.list-item {
  display: inline-block;
  display: block;
  width: 30%;
  background-color: bisque;
  font-size: 20px;
  padding: 10px 75px 10px 75px;
}
</style>
