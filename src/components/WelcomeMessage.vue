<script setup>
defineProps({
    msg: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <div class="greetings">
        <h1>{{ msg }}</h1>
    </div>
</template>

<style scoped></style>
