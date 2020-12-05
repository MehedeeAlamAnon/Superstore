<template>
    <ul class="list-group">
        
        <li class="list-group-item list-group-item d-flex justify-content-between">
            <span>Item</span>
            <span>Price</span>
        </li>

        <li v-for="(item,index) in items" :key="index" class="list-group-item d-flex justify-content-between">
            <span>{{item.title}}</span>
            <button class="btn btn-sm btn-danger" @click="removeItem(index)">-</button>
            <span>{{item.price}}</span>
        </li>

        <li class="list-group-item list-group-item d-flex justify-content-between">
            <span>Total</span>
            <span>{{totalPrice}}</span>
        </li>
    </ul>
</template>

<script>
export default {
    props:['items'],
    computed:{
        totalPrice(){
            var total=0
            this.items.forEach(item => {
                total=total+parseFloat(item.price)
            })
            return total
        }
    },
    methods:{
        removeItem(index){
            this.$emit('itemRemoved',index)
        }
    }
}
</script>

<style>

</style>