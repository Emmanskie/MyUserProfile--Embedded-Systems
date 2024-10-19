<template>
  <div class="video-background">
    <video autoplay muted loop class="background-video">
      <source src="@/assets/bg-contacts.mp4" type="video/mp4" />
      Your browser does not support the video tag.
    </video>
    <div class="container">
      <h2 class="contact-title">Contact Me</h2>
      <form @submit.prevent="submitForm" class="contact-form">
        <div class="mb-3">
          <label for="name" class="form-label">Name</label>
          <input type="text" class="form-control" id="name" v-model="form.name" required>
        </div>
        <div class="mb-3">
          <label for="email" class="form-label">Email</label>
          <input type="email" class="form-control" id="email" v-model="form.email" required>
        </div>
        <div class="mb-3">
          <label for="message" class="form-label">Message</label>
          <textarea class="form-control" id="message" rows="3" v-model="form.message" required></textarea>
        </div>
        <button type="submit" class="btn btn-primary">Send Message</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "ContactPage",
  data() {
    return {
      form: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  methods: {
    submitForm() {
      alert(`Message sent by ${this.form.name}`);
      // Handle form submission logic here
    },
  },
};
</script>

<style scoped>
.video-background {
  position: relative;
  height: 100vh; /* Full height to cover the screen */
  overflow: hidden; /* Prevent overflow */
}

.background-video {
  position: absolute;
  top: 50%;
  left: 50%;
  min-width: 100%;
  min-height: 100%;
  width: auto;
  height: auto;
  z-index: -1; /* Send video behind other content */
  transform: translate(-50%, -50%); /* Center the video */
}

.container {
  position: relative; /* Keep content above video */
  z-index: 1; /* Ensure content is above the video */
  padding: 2rem; /* Add padding for better spacing */
  background-color: rgba(0, 0, 0, 0.6); /* Semi-transparent background for readability */
  border-radius: 8px; /* Rounded corners for the form container */
}

.contact-title {
  color: white; /* Change font color to white */
  text-align: center; /* Center the title */
  margin-bottom: 20px; /* Space between title and form */
}

.contact-form {
  max-width: 600px; /* Limit the width of the form */
  margin: auto; /* Center the form */
}
</style>
