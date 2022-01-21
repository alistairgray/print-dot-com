<template>
    <main>
        <h2>Choose a product to start</h2>
        <h3>{{flyers.titlePlural}}</h3>
        <ul>
            <div>
                <div v-for="(property, index) in flyers.properties" :key="property.id" :selected="index">
                    <div class="flyer-property"><h2>Select your {{property.slug}}</h2></div>
                    <div @click="addToCart(property.slug, option.name)" class="flyer-option" v-for="option in property.options" :key="option.id">
                        <div class="flyer-unselected"><p>{{option.name}}</p></div>
                    </div>
                </div>
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
                     
                 },
                 cart: {}
            }
        },
        methods: {
            addToCart(propName, optionName) {
                this.flyerOptions = {
                    propName
                }
                this.flyerOptions.propName = optionName
            }
        }
    }
</script>


<style scoped>
    .flyer-property {
        
    }
    .flyer-option {
        display: inline-block;
        border: 3px solid white;
        min-width: 100px;
        max-width: 120px;
        margin: 5px;
        padding: 5px;
        border-radius: 15px;
    }
    .flyer-option:hover {
        background: white;
        color: navy;
        border: 3px solid navy;
    }
    .flyer-option-selected {
        background: white;
        color: navy;
        border: 3px  navy;
    }
    .flyer-option-hidden {
        display: none;
    }
</style>