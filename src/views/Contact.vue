<template>
  <div class="contact">
    <div class="contact-container">
      <div class="contact-header">
        <h1>Contact Us</h1>
        <p>Have questions or feedback? We'd love to hear from you.</p>
      </div>

      <div class="contact-content">
        <div class="contact-form">
          <h2>Send us a message</h2>
          <form @submit.prevent="submitForm">
            <div class="form-group">
              <label for="name">Your Name</label>
              <input type="text" id="name" v-model="form.name" required>
            </div>

            <div class="form-group">
              <label for="email">Email Address</label>
              <input type="email" id="email" v-model="form.email" required>
            </div>

            <div class="form-group">
              <label for="subject">Subject</label>
              <input type="text" id="subject" v-model="form.subject" required>
            </div>

            <div class="form-group">
              <label for="message">Message</label>
              <textarea id="message" v-model="form.message" rows="5" required></textarea>
            </div>

            <button type="submit" class="submit-button">Send Message</button>
          </form>
          <div class="form-status" v-if="formStatus">
            {{ formStatus }}
          </div>
        </div>

        <div class="contact-info">
          <h2>Our Information</h2>

          <div class="info-item">
            <div class="info-icon">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24">
                <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z" fill="currentColor"/>
              </svg>
            </div>
            <div>
              <h3>Email</h3>
              <p>ddgotobuy@ddgotobuy.fun</p>
            </div>
          </div>

          <div class="info-item">
            <div class="info-icon">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24">
                <path d="M11.99 2C6.47 2 2 6.48 2 12s4.47 10 9.99 10C17.52 22 22 17.52 22 12S17.52 2 11.99 2zM12 20c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8zm.5-13H11v6l5.25 3.15.75-1.23-4.5-2.67z" fill="currentColor"/>
              </svg>
            </div>
            <div>
              <h3>Business Hours</h3>
              <p>Monday - Friday: 9AM - 6PM<br>Saturday: 10AM - 4PM<br>Sunday: Closed</p>
            </div>
          </div>
        </div>
      </div>
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
        subject: '',
        message: ''
      },
      formStatus: ''
    }
  },
  methods: {
    submitForm() {
      // Here you would typically send the form data to an API
      console.log('Form submitted:', this.form)
      
      // Simulate form submission success
      this.formStatus = 'Thank you for your message! We will get back to you soon.'
      
      // Reset form after submission
      setTimeout(() => {
        this.form = {
          name: '',
          email: '',
          subject: '',
          message: ''
        }
      }, 1000)
    }
  }
}
</script>

<style scoped>
.contact {
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
}

.contact-container {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.contact-header {
  text-align: center;
  padding: 40px 20px;
  background-color: #f9f9f9;
}

.contact-header h1 {
  margin-bottom: 10px;
  color: #333;
}

.contact-header p {
  color: #666;
  font-size: 18px;
}

.contact-content {
  display: flex;
  flex-wrap: wrap;
}

.contact-form, .contact-info {
  flex: 1;
  min-width: 300px;
  padding: 40px;
}

.contact-form {
  border-right: 1px solid #eee;
}

.contact-form h2, .contact-info h2 {
  margin-top: 0;
  margin-bottom: 20px;
  color: #333;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  margin-bottom: 5px;
  font-weight: bold;
  color: #555;
}

.form-group input, .form-group textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 16px;
}

.form-group textarea {
  resize: vertical;
}

.submit-button {
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  transition: background-color 0.3s;
}

.submit-button:hover {
  background-color: #45a049;
}

.form-status {
  margin-top: 20px;
  padding: 10px;
  background-color: #e7f9e7;
  border-radius: 4px;
  color: #4CAF50;
}

.info-item {
  display: flex;
  margin-bottom: 30px;
}

.info-icon {
  margin-right: 15px;
  color: #4CAF50;
}

.info-item h3 {
  margin: 0 0 5px 0;
  color: #333;
}

.info-item p {
  margin: 0;
  color: #666;
  line-height: 1.5;
}

@media (max-width: 768px) {
  .contact-content {
    flex-direction: column;
  }
  
  .contact-form {
    border-right: none;
    border-bottom: 1px solid #eee;
  }
}
</style>
