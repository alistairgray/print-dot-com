<template>
    <main>
        <div>
            <div class="product-type">
                <!-- TODO: Dynamic Cards -->
                <h3>Business Cards</h3>
                <div class="product-image">
                    <img src="https://www.fillmurray.com/200/200" />
                </div>
            </div>
            <div class="product-type">
                <h3>Flyers</h3>
                <div class="product-image">
                    <img src="https://www.fillmurray.com/200/200" />
                </div>
            </div>
            <div class="product-type">
                <h3>Posters</h3>
                <div class="product-image">
                    <img src="https://www.fillmurray.com/200/200" />
                </div>
            </div>
        </div>
    </main>
</template>

<script>
    import flyers from '../json/flyers.json'
    import businessCards from '../json/businesscards.json'
    import posters from '../json/posters.json'

    export default {
        data() {
            return {
                flyers: flyers,
                businessCards: businessCards,
                posters: posters
            }
        }
        
    }
</script>


<style scoped>
    .product-type {
        display: inline-block;
        margin: 15px;
    }
</style>