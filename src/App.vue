<script setup>
import WelcomeMessage from "./components/WelcomeMessage.vue";
import ShoeList from "./components/ShoeList.vue";
import ContactUs from "./components/ContactUs.vue";
</script>

<template>
    <header class="header">
        <img
            alt="Nike logo"
            class="logo"
            src="https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5362a828-0f5b-4d17-a6c5-d0677dc89baa_1000x1000.jpeg"
            width="125"
            height="125"
        />

        <div class="greetings">
            <h1>Welcome to our shoe shop</h1>
        </div>
    </header>

    <main class="main-content">
        <ShoeList />
    </main>
</template>

<style scoped>
/* Style for the header to stack on top */
.header {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #f4f4f4;
    padding: 1rem;
    border-bottom: 2px solid #ddd;
    text-align: center;
}
.logo {
    margin-bottom: 1rem;
    border-radius: 50%;
}

/* Style for the greetings */
.greetings h1 {
    font-size: 2rem;
    color: #333;
}

/* Style for main content */
.main-content {
    padding: 2rem;
    background-color: #fff;
}
</style>
