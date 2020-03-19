
<template>
  <div id="app">
    <div class="cart-container">
      <cart :owner_data="{name:'Boss Nath', loc:'Phil'}" :items_data="this.toadd"></cart>
    </div>
    <div class="store-container">
      <store :storename_data="'Tindahan ni Aleng Nena'" :products_data="[{name:'alcohol', price:1000}, {name:'facemask', price:1000000}, 
      {name:'meats', price: 0.50}]" v-on:addProd="addItem($event)"></store>
      <store :storename_data="'Tindahan ni Amparing'" :products_data="[{name:'bodka', price:12}, {name:'medyas', price:9}, 
      {name:'glock', price: 0.50}]" v-on:addProd="addItem($event)"></store>
      <store :storename_data="'Tindahan ni Aling Puring'" :products_data="[{name:'imported alcohol from china', price:50}, {name:'facemask made out of mammoth fur', price:10}, 
      {name:'sabertooth tiger meat', price: 990}]" v-on:addProd="addItem($event)"></store>
    </div>
  </div>
</template>

<script>
import Store from "./components/Store.vue";
import Cart from "./components/Cart.vue";

export default {
  components : {
    'store':Store,
    'cart':Cart,
  },
  name: 'app',
  data () {
    return {
        toadd : []
    }
  },
  methods : {
    addItem : function(e) {
      this.toadd.push(e);
    }
  }
}
</script>

<style lang="scss">
li {font-family: 'Avenir', Helvetica, Arial, sans-serif;}
.cart-container { margin-bottom: 12px;
  div {background: #111; color: white; padding: 12px;
    ul {padding: 0 12px; height: 120px; overflow: auto;
      li {width: 100%; list-style: none; margin: 5px 0}
    }
  }
}
.store-container {width: 100%; display: flex; justify-content: space-between;
  div:first-child {background: #644D3C}
  div:last-child {background: #C6C97B;}
  div:nth-child(2) {background:#A7B39B; margin: 0 12px}
  div {padding: 24px; width: 100%; max-width: 31%;}
  div ul {height: 200px;overflow: auto; padding: 0 12px 0 0;}
  div ul li {position: relative; margin: 9px 0}
  div ul li p {display: inline-block; margin: 0}
  div ul li p:first-child { min-width: 100px;}
  div ul li button {position: absolute; right: 0}
}
</style>
