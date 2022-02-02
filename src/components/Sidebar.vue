<template>
    <aside class="cart-container">
        <div class="cart">
            <h1>
                <span>Cart</span>
                <button @click="toggleCart" class="cart-close">&times;</button>
            </h1>
            <div class="cart-body">
                <table class="cart-table">
                    <thead>
                        <tr>
                            <th>Chosen Flyer</th>
                            <th>Size</th>
                        </tr>
                        <tbody>
                            <tr v-for="(property, option, index) in cart" :key="index">
                                <td>{{property}}</td>
                                <td>{{option}}</td>
                            </tr>
                        </tbody>
                    </thead>
                </table>
            </div>
        </div>
    </aside>
</template>

<script>
    export default {
        props: ["toggleCart","cart"]
    }
</script>