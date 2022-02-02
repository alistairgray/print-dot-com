<template>
    <Sidebar />
    <main>
        <h2>Choose a product to start</h2>
        <h3>{{flyers.titlePlural}}</h3>
        <div class="flyer-options-selection">
            <div class="flyer-options-selected" v-for="property in flyers.properties" :key="property.id"><strong>Flyer {{property.slug}}:</strong> {{cart[property.slug]}}</div>
        </div>
            <div>
                <div v-for="(property, index) in flyers.properties" :key="property.id" :selected="index" ref="index">
                    <div class="flyer-property"><h2>Select your {{property.slug}}</h2></div>
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
    </main>
</template>

<script>
    import Sidebar from '../components/Sidebar.vue'
    import Flyers from '../json/flyers.json'
    export default {
        name: 'Products',
        components: {
            Sidebar
        },
        data() {
            return {
                flyers: Flyers,
                cart: {}
            }
        },
        methods: {
            addToCart(propName, optionName) {
                this.cart[propName] += optionName
            },
            removeOptions(selected) {
                this.$refs.index[selected].style.display = "none";
            }
        }
    }
</script>


<style scoped>

    .flyer-option, .flyer-options-selected{
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
    .flyer-options-selected {
        border: solid yellow;
        padding: 15px;
    }
</style>