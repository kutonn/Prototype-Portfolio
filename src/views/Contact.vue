<template>
  <div class="page fade-in">
    <h1><center>Contact Me</center></h1>

    <div class="contact-box">
      <form @submit.prevent="submitForm" class="contact-form">
        <input type="text" placeholder="Name" v-model="form.name" required />
        <input type="email" placeholder="Email" v-model="form.email" required />
        <textarea placeholder="Message" v-model="form.message" rows="5" required></textarea>
        <button type="submit">Send</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      console.log(this.form)
      alert('Form submitted! (Demo only)')
      this.form.name = ''
      this.form.email = ''
      this.form.message = ''
    }
  }
}
</script>

<style scoped>
.page {
  padding: 2rem;
  font-family: Arial, sans-serif;
}

.contact h1 {
  text-align: center;
  margin-bottom: 2rem;
}

/* Box container */
.contact-box {
  max-width: 500px;
  margin: 0 auto;
  background-color: #f9f9f9; /* light box background */
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

/* Form styling */
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-form input,
.contact-form textarea {
  padding: 0.75rem 1rem;
  border: 1px solid #ccc;
  border-radius: 8px;
  font-size: 1rem;
  width: 100%;
  box-sizing: border-box;
  transition: border-color 0.2s;
}

.contact-form input:focus,
.contact-form textarea:focus {
  outline: none;
  border-color: #004F98;
}

.contact-form button {
  padding: 0.75rem 1rem;
  background-color: #5D8AA8;
  color: white;
  font-size: 1rem;
  font-weight: 500;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.contact-form button:hover {
  background-color: #004F98;
}
</style>
