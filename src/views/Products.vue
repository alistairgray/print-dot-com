<template>
    <main>
        <h2>Choose a product to start</h2>
        <h3>{{flyers.titlePlural}}</h3>
        <ul>
            <div>
                <div v-for="(property, index) in flyers.properties" :key="property.id" ref="index">
                    <div class="flyer-property"><h2>Select your {{property.slug}}</h2><p>Selected: {{cart.size}}</p></div>
                    <div @click="
                        addToCart(property.slug, option.name); 
                        removeOptions(index)" 
                        class="flyer-option" 
                        v-for="option in property.options" :key="option.id"
                        >
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
                cart: {}
            }
        },
        methods: {
            addToCart(propName, optionName) {
                if (!this.cart[propName]) this.cart[propName] = 0
                    this.cart[propName] += optionName
            },
            removeOptions(selected) {
                console.log(`DIV Number ${selected} selected!`);
                console.log();
                this.$refs.selected.style.display = "none";
            }
        }
    }
</script>


<style scoped>

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
</style>