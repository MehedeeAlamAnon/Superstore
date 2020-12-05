<template>

    <div class="row">
        <div class="col-sm-4" v-for="(item,index) in items" :key="index">
            <div class="card">
                <img :src="item.photo" class="card-img-top" alt="...">
                <div class="card-body">
                <h5 class="card-title">{{item.title}}</h5>
                <p class="card-text">{{item.price}}</p>
                <a @click="addToCart(item)" class="btn btn-primary">+ADD</a>
                </div>
            </div>
        </div>
    </div>
    
</template>

<script>
export default {
    props:['items'],
    methods:{
        addToCart(item){
            this.$emit('newItemAdded',item)
        }
    }
}
</script>

<style>

</style>