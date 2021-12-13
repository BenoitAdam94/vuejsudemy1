<template>
<!-- eslint-disable vue/no-use-v-if-with-v-for,vue/no-confusing-v-for-v-if -->
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p v-if="myArray" v-for="(el, index) in myArray" :key="index">{{ el }}</p>
    <button type="button" @click="addFruits">Add Fruits</button>
    <slot name="info"></slot>
    <slot name="footer"></slot>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    myArray: Array
  },
  methods: {
    addFruits() {
      let fruitsList = ["Pommes", "Poires", "Oranges"]
      this.$emit('addFruitToBasket', fruitsList[Math.floor(Math.random() * fruitsList.length)])

      // console.log(fruitsList[Math.floor(Math.random() * fruitsList.length)])
      // console.log("tamere")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
