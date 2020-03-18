<template>
<div>
    <h1>Hey there, {{owner.name}}!</h1>
    <p>you have {{items.length}} items</p>
    <ul class="cart-cont">
        <li v-for="i in items" :key="i">{{i.name}}</li>
    </ul>
</div>
</template>

<script>
export default {
    props : {
        owner_data : {
            type: Object,
            default: function() {
                return {name:"Owner", loc:"Phil"}
            }
        },
        items_data : {
            type: Array,
            default : function() {return []}
        }
    },
    data : function() {
        return {
            items : this.items_data,
            owner : this.owner_data
        }
    }
}
</script>