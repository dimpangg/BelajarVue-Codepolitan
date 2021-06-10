<template>
    <div>
        <h1>Checkout</h1>
        <table class="table" v-if="cart.length">
            <caption class="text-right h3">
                <b>Total:</b>
                <price class="d-block text-success font-weight-light" :value="Number(cartTotal)"></price>
            </caption>
            <thead>
                <tr>
                    <th></th>
                    <th>Item</th>
                    <th>Qty</th>
                    <th>Price</th>
                    <th>Sub Total</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, index) in cart" :key="item.product.id">
                    <td class="text-center">
                        <div class="btn-group">
                            <button class="btn btn-info" @click="$emit('add', item.product)">+</button>
                            <button class="btn btn-outline-info" @click="$emit('delete', index)">-</button>
                        </div>
                    </td>
                    <th>{{ item.product.name }}</th>
                    <th>{{ item.qty }}</th>
                    <th>{{ Number(item.product.price) }}</th>
                    <th>
                        {{ Number(item.product.price * item.qty) }}
                    </th>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import Price from "./Price.vue"

export default {
    name: "checkout",
    props: ["cart", "cartTotal"],
    components: {
        Price
    }
}
</script>