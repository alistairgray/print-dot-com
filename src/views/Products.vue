<template>
    <main>
        <h2>Choose a product to start</h2>
        <h3>{{flyers.titlePlural}}</h3>
        <p><strong>Flyer Properties</strong></p>
        <ul>
            <div class="product-option">
            <li v-for="property in flyers.properties" :key="property.id">
                <label>Choose a {{property.slug}}</label>
                <br />
                <select v-model="selected">
                    <option v-for="option in property.options" :key="option.id">{{option.slug}}</option>
                </select>
            </li>
            </div>
        </ul>
    </main>
</template>

<script>
    import Flyers from '../json/flyers.json'
    export default {
        name: 'Products',
        components: {
        },
        data() {
            return {
                 flyers: Flyers,
                 flyerOptions: {
                     size: ''
                 },
                 cart: {}
            }
        },
        methods: {

        }
    }
</script>


<style scoped>
    li {
        list-style: none;
        border: 7px dashed yellow;
        display: inline-block;
        margin: 15px;
    }   
</style>