
<template>
  <div id="app">
    <cart :owner_data="{name:'Lord Nath', loc:'Phil'}" :items_data="this.toadd"></cart>
    <store :storename_data="'Tindahan ni Aleng Nena'" :items_data="[{name:'alcohol', price:1000}, {name:'facemask', price:1000000}, 
    {name:'meats', price: 0.50}]" v-on:addProd="addItem($event)"></store>
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
</style>
