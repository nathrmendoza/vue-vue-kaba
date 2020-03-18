<template>
<div>
    <h1>{{storename}}</h1>
    <ul class="store-inner">
        <li v-for="(prod,index) in products" :key="prod"> {{prod}} <button @click="addProd(index)">+</button></li>
    </ul>
</div>
</template>

<script>
export default {
    props : {
        products_data : {
            type : Array,
            default : function() {
                return [{name: "alcohol", price:1}, {name:"bygon", price:1}, {name:"facemask",price:1}]
            }
        },
        storename_data : {
            type : String,
            default : "New Store"
        }
    },
    data : function() {
        return {
            products : this.products_data,
            storename : this.storename_data
        }
    },
    methods : {
        addProd : function(i) {
            this.$emit("addProd", this.products[i]);
        }
    }
}
</script>