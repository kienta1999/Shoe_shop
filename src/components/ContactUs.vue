<template>
    <div class="contact-form">
        <h2>Get in touch to explore our exclusive shoes options</h2>
        <form @submit.prevent="submitForm">
            <div>
                <p v-if="formData.message != null" class="message">{{ formData.message }}</p>
            </div>
            <div class="form-group">
                <label for="name">Name:</label>
                <input type="text" id="name" v-model="formData.name" class="form-control" placeholder="Enter your name" required />
            </div>
            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" v-model="formData.email" class="form-control" placeholder="Enter your email" required />
            </div>
            <div class="form-group">
                <label for="phone">Phone Number:</label>
                <input type="tel" id="phone" v-model="formData.phone" class="form-control" placeholder="Enter your phone number" required />
            </div>
            <button type="submit" class="btn-submit">Submit</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            formData: {
                name: "",
                email: "",
                phone: "",
                message: null,
            },
        };
    },
    methods: {
        submitForm() {
            console.log("Form submitted:", this.formData);
            this.formData.message = `Thank you ${this.formData.name} for contacting us. We will email you at ${this.formData.email} and text you at ${this.formData.phone} about our newest shoes.`;
        },
    },
};
</script>

<style scoped>
.contact-form {
    max-width: 600px;
    margin: 2rem auto;
    padding: 2rem;
    background-color: #f9f9f9;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

h2 {
    text-align: center;
    margin-bottom: 1.5rem;
    color: #333;
}

.form-group {
    margin-bottom: 1.5rem;
}

label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: bold;
}

input[type="text"],
input[type="email"],
input[type="tel"] {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #ddd;
    border-radius: 5px;
    font-size: 1rem;
}

input:focus {
    border-color: #007bff;
    outline: none;
    box-shadow: 0 0 5px rgba(0, 123, 255, 0.5);
}

.btn-submit {
    display: block;
    width: 100%;
    padding: 0.75rem;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1rem;
    cursor: pointer;
}

.btn-submit:hover {
    background-color: #0056b3;
}

.message {
    color: red;
}
</style>
