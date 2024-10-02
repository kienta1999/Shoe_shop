<script setup>
import ShoeItem from "./ShoeItem.vue";
import ContactUs from "./ContactUs.vue";
</script>

<script>
export default {
    data() {
        return {
            shoeList: [
                { shoeName: "shoe1", price: 50, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/e777c881-5b62-4250-92a6-362967f54cca/WMNS+AIR+FORCE+1+%2707.png" },
                { shoeName: "shoe2", price: 60, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/720dd9b1-41bb-40e9-8d5f-cebb4e16799b/AIR+FORCE+1+%2707+LV8.png" },
                { shoeName: "shoe3", price: 70, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/c20afd60-b230-4815-bfd2-6768c875f6cd/AIR+FORCE+1+%2707.png" },
                { shoeName: "shoe4", price: 80, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/2d216a2a-d2e2-4d36-a095-15cd7bc4bc16/W+AF1+SHADOW.png" },
                { shoeName: "shoe5", price: 90, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/76c12aad-43cd-4e4f-aeb0-44b45f6f805e/AIR+FORCE+1+LOW+RETRO.png" },
                { shoeName: "shoe6", price: 100, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/549c58b4-8d4d-4121-86c5-dc16aaa048ea/AIR+FORCE+1+LOW+RETRO+QS.png" },
                { shoeName: "shoe7", price: 50, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/e777c881-5b62-4250-92a6-362967f54cca/WMNS+AIR+FORCE+1+%2707.png" },
                { shoeName: "shoe8", price: 60, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/720dd9b1-41bb-40e9-8d5f-cebb4e16799b/AIR+FORCE+1+%2707+LV8.png" },
                { shoeName: "shoe9", price: 70, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/c20afd60-b230-4815-bfd2-6768c875f6cd/AIR+FORCE+1+%2707.png" },
                { shoeName: "shoe10", price: 80, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/2d216a2a-d2e2-4d36-a095-15cd7bc4bc16/W+AF1+SHADOW.png" },
                { shoeName: "shoe11", price: 90, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/76c12aad-43cd-4e4f-aeb0-44b45f6f805e/AIR+FORCE+1+LOW+RETRO.png" },
                { shoeName: "shoe12", price: 100, url: "https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/549c58b4-8d4d-4121-86c5-dc16aaa048ea/AIR+FORCE+1+LOW+RETRO+QS.png" },
            ],
            currentIndex: 0,
        };
    },
    methods: {
        nextSlide() {
            this.currentIndex = (this.currentIndex + 1) % this.shoeList.length;
        },
        prevSlide() {
            this.currentIndex = (this.currentIndex - 1) % this.shoeList.length;
        },
    },
};
</script>

<template>
    <div class="slideshow-and-contact-us">
        <div class="slideshow">
            <h1>A slideshow of our hottest shoes</h1>
            <div class="slides">
                <img :src="shoeList[currentIndex].url" :alt="shoeList[currentIndex].shoeName" class="shoe-image" />
            </div>
            <div class="controls">
                <button @click="prevSlide">Previous</button>
                <button @click="nextSlide">Next</button>
            </div>
        </div>
        <div class="contact-us">
            <ContactUs />
        </div>
    </div>
    <div class="shoe-grid">
        <ShoeItem v-for="({ shoeName, price, url }, index) in shoeList" :key="index" :shoeName="shoeName" :price="price" :url="url" />
    </div>
</template>

<style scoped>
.shoe-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 3 items per row */
    gap: 20px; /* Spacing between the grid items */
    margin: 20px;
}
.slideshow {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 45%;
}
.shoe-image {
    width: 300px;
    height: auto;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.shoe-info {
    margin-top: 10px;
    text-align: center;
}

.controls {
    margin-top: 20px;
}
button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 10px 20px;
    margin: 0 10px;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
.slideshow-and-contact-us {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 40px; /* Adds space between the slideshow and the contact form */
    padding: 20px;
}
.contact-us {
    width: 45%;
}
</style>
