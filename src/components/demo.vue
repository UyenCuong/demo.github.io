<template>
  <div class="demo">
      <h1>Việc cần làm</h1>
      <span>Message: {{ msg }}</span>
      <p v-once>This will never change: {{ msg }}</p>
      <p v-bind:title="message">
    Hover your mouse over me for a few seconds to see my dynamically bound
    title!
      </p>
      <a :href="url">Made by Vue Mastery</a>
      <div><p v-if="inventory > 10">In Stock</p>
      <p v-else-if="inventory <= 10 && inventory > 0">Almost sold out!</p>
      <p v-else>Out of Stock</p>
      </div>
      <div>
            <ul v-for="(item, index) in items" :key="item.id">
            <li >
                {{ parentMessage }} - {{ index }} - {{ item.message }}
            </li>
            </ul>
      </div>
        <p v-if="onSale">On Sale!</p>
        <button  @click="addToCart">Add to Cart</button>
        
  </div>
</template>

<script>
export default {
    name:'demo',
    data(){
        return {
            msg : 'Hello VueJs',
            url: 'https://www.vuemastery.com/',
            message: 'You loaded this page on ' + new Date().toLocaleString(),
            inventory: 100,
            onSale: false,
            parentMessage: 'Parent',
            items: [{ message: 'Foo' }, { message: 'Bar' }],
        } 
    },
    methods: {
        addToCart() {
            this.cart += 1
        },
        
    }
}
</script>

<style scoped>
.demo{
    background: rgba(85, 238, 230, 0.333);
}
</style>