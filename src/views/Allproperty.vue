<template>
    <div> All Properties </div>
    <div class="products-container">
        <div v-for="property of properties" :key="property.id" class="card">
            <img src="property.image" alt="property.address.street"/>
            {{property.address.street}}
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            properties: []
        }
    },
    mounted() {
        fetch("http://localhost:3000/properties")
            .then((res) => res.json())
            .then((data) => (this.properties = data));
    },
};
</script>



<style>

</style>
