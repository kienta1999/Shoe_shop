<script setup>
defineProps({
    shoeName: {
        type: String,
        required: true,
    },
    price: {
        type: Number,
        required: true,
    },
    url: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <div class="item">
        <img :src="url" :alt="shoeName" class="item-image" />
        <div class="item-info">
            <h2 class="item-name">{{ shoeName }}</h2>
            <p class="item-price">Price: ${{ price }}</p>
        </div>
    </div>
</template>

<style scoped>
.item {
    margin-top: 2rem;
    display: flex;
    align-items: center;
    background-color: #f9f9f9;
    padding: 1rem;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s ease-in-out;
}
.item:hover {
    transform: scale(1.05);
}
.item-image {
    width: 150px;
    height: 150px;
    object-fit: cover;
    border-radius: 10px;
    margin-right: 2rem;
}
.item-info {
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.item-name {
    font-size: 1.5rem;
    color: #333;
    margin-bottom: 0.5rem;
}
.item-price {
    font-size: 1.25rem;
    color: #555;
}
</style>
