<template>
  <div class="contact-container">
    <h2>Contact</h2>
    <p>If you'd like to reach out, please fill out the form below or check out my socials :)</p>

    <form @submit.prevent="submitForm" class="contact-form">
      <div class="form-group">
        <label for="name">Name</label>
        <input type="text" id="name" v-model="formData.name" required />
      </div>

      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" v-model="formData.email" required />
      </div>

      <div class="form-group">
        <label for="message">Message</label>
        <textarea id="message" v-model="formData.message" rows="5" required></textarea>
      </div>

      <button type="submit">Send</button>
    </form>

    <!-- Success Popup -->
    <div v-if="success" class="popup">
      <p>Message sent successfully!</p>
      <button @click="success = false">Close</button>
    </div>

    <!-- Social icons -->
    <div class="social-icons">
      <a href="https://x.com/mitchell_wo" target="_blank" rel="noopener noreferrer">
        <img src="@/assets/twitter.png" alt="Twitter" class="icon" />
      </a>
      <a href="https://github.com/Mitch-Wohead" target="_blank" rel="noopener noreferrer">
        <img src="@/assets/github.png" alt="GitHub" class="icon" />
      </a>
      <a href="https://linkedin.com/in/mitchell-wohead-47aa3316a" target="_blank" rel="noopener noreferrer">
        <img src="@/assets/linkdin.png" alt="LinkedIn" class="icon" />
      </a>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Reactive state for form data and success message
const formData = ref({
  name: '',
  email: '',
  message: '',
});

const success = ref(false);

const submitForm = async () => {
  try {
    const response = await fetch('https://formspree.io/f/mbldjrqq', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(formData.value),
    });

    if (response.ok) {
      success.value = true; // Show success popup
      formData.value = { name: '', email: '', message: '' }; // Clear form
    } else {
      console.error('Failed to send message:', await response.text());
    }
  } catch (error) {
    console.error('Error sending message:', error);
  }
};
</script>

<style scoped>

.social-icons {
  margin-top: 2rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem; /* Space between icons */
}

.icon {
  width: 40px; /* Adjust icon size */
  height: 40px;
  transition: transform 0.3s ease, opacity 0.3s;
  cursor: pointer;
}

.icon:hover {
  transform: scale(1.2); /* Slight zoom effect */
  opacity: 0.8; /* Dim the icon slightly */
}
.contact-container {
  padding: 2rem;
  text-align: center;
}

h2 {
  font-size: 2.5rem; /* Make the text larger */
  font-weight: 800; /* Bold and prominent */
  color: #333; /* Dark gray for a clean look */
  margin-bottom: 1.5rem; /* Increase spacing below */
  text-transform: uppercase; /* Optional: Make the text all caps */
  letter-spacing: 0.05rem; /* Add spacing between letters */
  text-align: Center;

}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 500px;
  margin: 0 auto;
}

.form-group {
  display: flex;
  flex-direction: column;
  text-align: left;
}

label {
  margin-bottom: 0.5rem;
  font-weight: bold;
}

input, textarea {
  padding: 0.5rem;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 1rem;
}

button {
  padding: 0.7rem 1.5rem;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #0056b3;
}

/* Success Popup */
.popup {
  margin-top: 2rem;
  padding: 1rem;
  background-color: #d4edda;
  color: #155724;
  border: 1px solid #c3e6cb;
  border-radius: 5px;
}
</style>