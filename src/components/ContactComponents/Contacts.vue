<template>
  <div class="contact-page">
    <h1>Contact Us</h1>
    <div class="contact-info">
      <h2>Contact Information</h2>
      <p><strong>Address:</strong> 123 Furniture Street, Suite 456, City, Country</p>
      <p><strong>Phone:</strong> +1 (123) 456-7890</p>
      <p><strong>Email:</strong> info@panto.com</p>
      <p><strong>Working Hours:</strong> Mon-Fri 9:00 AM - 6:00 PM</p>
    </div>
    <div class="contact-form">
      <h2>Get in Touch</h2>
      <form @submit.prevent="submitForm">
        <div>
          <label for="name">Name</label>
          <input type="text" id="name" v-model="form.name" required>
        </div>
        <div>
          <label for="email">Email</label>
          <input type="email" id="email" v-model="form.email" required>
        </div>
        <div>
          <label for="phone">Phone</label>
          <input type="tel" id="phone" v-model="form.phone">
        </div>
        <div>
          <label for="message">Message</label>
          <textarea id="message" v-model="form.message" required></textarea>
        </div>
        <button type="submit">Send Message</button>
      </form>
    </div>
    <div class="map">
      <h2>Find Us</h2>
      <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3153.0920260147274!2d144.95373581535626!3d-37.81627984235595!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6ad642af0f11fd81%3A0xf577f3b6d1d9b8b3!2sFederation+Square!5e0!3m2!1sen!2sau!4v1487742250135" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        message: ''
      }
    };
  },
  methods: {
    submitForm() {
      console.log('Form submitted:', this.form);
      alert('Thank you for your message! We will get back to you soon.');
      this.form.name = '';
      this.form.email = '';
      this.form.phone = '';
      this.form.message = '';
    }
  }
};
</script>

<style scoped>
.contact-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  color: white;
  text-shadow:
      -1px -1px 0 black,
      1px -1px 0 black,
      -1px 1px 0 black,
      1px 1px 0 black;
}

.contact-info, .contact-form, .map {
  margin-bottom: 40px;
}

.contact-form form {
  display: flex;
  flex-direction: column;
}

.contact-form div {
  margin-bottom: 20px;
}

.contact-form label {
  margin-bottom: 5px;
}

.contact-form input,
.contact-form textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.contact-form button {
  padding: 10px 20px;
  background-color: rgba(250, 159, 4, 0.85);
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.contact-form button:hover {
  background-color: rgba(250, 159, 4, 0.85);
}

.social-media a {
  display: inline-block;
  margin-right: 10px;
  color: rgba(250, 159, 4, 0.85);
}

.social-media a:hover {
  text-decoration: underline;
}
.map h2{
  padding-bottom: 20px;
}
</style>
