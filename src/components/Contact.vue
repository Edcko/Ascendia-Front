<template>
    <section id="contact" class="contact-section">
        <div class="background-image"></div>
        <div class="content">
            <h2>Contact Us</h2>
            <form @submit.prevent="handleSubmit">
                <div class="form-group">
                    <label for="name">Name:</label>
                    <input type="text" id="name" name="name" v-model="form.name" required />
                </div>
                <div class="form-group">
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email" v-model="form.email" required />
                </div>
                <div class="form-group">
                    <label for="phone">Phone:</label>
                    <input type="tel" id="phone" name="phone" v-model="form.phone" />
                </div>
                <div class="form-group">
                    <label for="subject">Subject:</label>
                    <input type="text" id="subject" name="subject" v-model="form.subject" />
                </div>
                <div class="form-group">
                    <label for="message">Message:</label>
                    <textarea id="message" name="message" v-model="form.message" required></textarea>
                </div>
                <button type="submit">Send</button>
            </form>
            <div v-if="message" class="success-message">{{ message }}</div>
        </div>
    </section>
</template>
  
<script>
import { ref } from 'vue';

export default {
    name: "ContactForm",
    setup() {
        const form = ref({
            name: '',
            email: '',
            phone: '',
            subject: '',
            message: ''
        });

        const message = ref('');

        const handleSubmit = () => {
            // Aquí puedes manejar el envío del formulario, por ejemplo, enviándolo a una API.
            console.log('Form data:', form.value);
            message.value = 'Thank you for contacting us!';
            form.value = {
                name: '',
                email: '',
                phone: '',
                subject: '',
                message: ''
            };
        };

        return {
            form,
            message,
            handleSubmit
        };
    }
};
</script>
  
<style scoped>
.contact-section {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-end;
    height: 100vh;
    position: relative;
    margin-bottom: 50px;
    /* Espacio entre el contacto y el footer */
}

.background-image {
    background: url('@/assets/background.jpg') no-repeat center center;
    background-size: cover;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 50%;
}

.content {
    position: relative;
    z-index: 1;
    background-color: rgba(240, 252, 254, 0.9);
    /* Fondo semi-transparente */
    padding: 2rem;
    width: 80%;
    max-width: 600px;
    margin-top: -35%;
    /* Ajustar para superponer la imagen de fondo y estar más arriba */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    border-radius: 8px;
}

.form-group {
    margin-bottom: 1rem;
}

.form-group label {
    display: block;
    margin-bottom: 0.5rem;
    color: #333333;
    /* Gris Oscuro */
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 0.5rem;
    border: 1px solid #ccc;
    border-radius: 4px;
}

button {
    background-color: #0C3756;
    /* Azul Profundo */
    color: white;
    padding: 0.75rem 1.5rem;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #1F5372;
    /* Azul Oscuro */
}

.success-message {
    margin-top: 1rem;
    color: #1F5372;
    /* Azul Oscuro */
}</style>
  