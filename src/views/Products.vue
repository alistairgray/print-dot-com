<template>
    <main>
        <h1>Product Builder</h1>
        <h2>Choose a product to start</h2>
        <img src="https://www.fillmurray.com/200/200" />
        <h3>{{flyers.titlePlural}}</h3>
        <p><strong>Flyer Properties</strong></p>
        <ul v-for="property in flyers.properties" :key="property.id">
            <div class="product-option">
            <li>
                <label>Choose a {{property.title}}</label>
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
                 flyers: Flyers
            }
        },
    }
</script>


<style scoped>
    li {
        list-style: none;
        border: 1px solid black;
    }   
    .product-option {
        display: inline-block;
        margin: 15px;
    }
</style>