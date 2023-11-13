<script setup>
  import { ref } from 'vue'

  let qty = ref (2)

  function addValue() {
    qty.value++
    console.log(qty)
  }
  function subtractvalue() {
    if (qty.value > 0) {
      qty.value--
      console.log(qty)
    }
  }
</script>

<template>
  <div class="wrapper">
    <div class="profaile">
      <div class="ballon" v-show="qty > 0">{{ qty }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="subtractvalue">-</div>
      <div class="button" @click="addValue">+</div>
    </div>

    <div  class="centrar" v-if="qty > 0">Me escrbieron 😊</div>
    <div class="centrar" v-else> No me escribieron 😒</div>
    
  </div>
</template>

<style scoped>
.centrar{
  text-align: center;
  background-color: beige;
}
  .button { 
    width: 32px;
    background-color: rgb(158, 37, 37);
    display: inline-block;
    padding: 4px 0;
    border-radius: 4px;
    margin: 0 8px;
  }
  .button:hover{
    cursor: pointer;
    background-color: rgb(204, 6, 6);
  }
  .button-wrapper{
    text-align: center;
    color: aliceblue;
    margin-top: 16px;
    margin-bottom: 16px;
  }
  .ballon{
    position: absolute;
    top: 0;
    right: 0;
    width: 32px;
    height: 32px;
    background-color: aqua;
    border-radius: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
  }
  .profaile{
    background-image: url("https://w7.pngwing.com/pngs/415/765/png-transparent-user-profile-linkedin-netwerk-money-order-fulfillment-round-face-saving-expert-moustache.png");
    background-size: cover;
    position: relative;
    background-color: blueviolet;
    width: 250px;
    height: 250px;
    border-radius: 100%;
    margin: auto;
  }
  .wrapper{
    overflow: hidden;
    background-color: rgb(66, 73, 73);
    width: 70%;
    border-radius: 20px;
    margin: 0 auto;
  }
</style>
