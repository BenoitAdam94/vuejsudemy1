<template>
  <div id="Home">
      <HelloWorld msg="Panier" :myArray="fruits" @addFruitToBasket="addThisFruit">
          <p slot="footer">Ceci est mon footer</p>
          <h2 slot="info">cECI ESt mon info</h2>
        </Helloworld>
        <p>Total : {{ calculateTVA }} euros</p>
        <p @click="increase">Augmenter le prix</p>
  </div>
</template>

<script>
import HelloWorld from '../components/HelloWorld.vue'

export default {
 name: "Home",
 components: {
     HelloWorld
 },
 computed: {
     calculateTVA() {
         return ((this.price / 100) * this.tva) + this.price
     }
 },
 data() {
     return {
         hello: 'world',
         price: 15,
         tva: 20,
         fruits: [
             "Bananes", "kiwis"
         ],
         newfruits: [
             "Pomme", "Poire"
         ]
     }
 },
 watch: {
     price: function() {
         console.log("le prix a augmenté")
     }
 },
 methods: {
     addThisFruit(fruit) {
        this.fruits.push(fruit)
     },
     increase() {
         this.price++
     }
 }
}
</script>

<style>

</style>