<template>
  <div>
    <!-- Video Background -->
    <video class="video-background" autoplay muted loop>
      <source src="../assets/bg-aboutme.mp4" type="video/mp4" />
      Your browser does not support the video tag.
    </video>

    <!-- Dashboard-like Layout -->
    <AppNavbar />
    <AppSidebar />
    
    <!-- Main Content Area -->
    <div class="content">
      <div class="about-me-container">
        <h2 class="title animated-fade-in">About Me</h2>

        <!-- Cards Section -->
        <div class="card-grid">
          <!-- Background Card -->
          <div class="card text-white bg-primary shadow-sm animated-card">
            <div class="card-body">
              <h5 class="card-title">Background</h5>
              <p class="card-text">I'm a computer engineering student with a passion for IoT and software development.</p>
              <i class="bi bi-book card-icon"></i>
            </div>
          </div>

          <!-- Hobbies Card -->
          <div class="card text-white bg-success shadow-sm animated-card">
            <div class="card-body">
              <h5 class="card-title">Hobbies</h5>
              <p class="card-text">I enjoy going to the gym and working on personal tech projects in my spare time.</p>
              <i class="bi bi-bicycle card-icon"></i>
            </div>
          </div>

          <!-- Interests Card -->
          <div class="card text-white bg-warning shadow-sm animated-card">
            <div class="card-body">
              <h5 class="card-title">Interests</h5>
              <p class="card-text">My main interests include IoT, automation, and helping others through tech innovations.</p>
              <i class="bi bi-lightbulb card-icon"></i>
            </div>
          </div>

          <!-- Future Goals Card -->
          <div class="card text-white bg-danger shadow-sm animated-card">
            <div class="card-body">
              <h5 class="card-title">Future Goals</h5>
              <p class="card-text">I aim to develop impactful IoT solutions for real-world problems in agriculture and beyond.</p>
              <i class="bi bi-flag card-icon"></i>
            </div>
          </div>

          <!-- Fun Fact Card -->
          <div class="card text-white bg-info shadow-sm animated-card">
            <div class="card-body">
              <h5 class="card-title">Fun Fact</h5>
              <p class="card-text">I love and enjoy playing sports and games that involve teamwork.</p>
              <i class="bi bi-trophy card-icon"></i>
            </div>
          </div>

          <!-- Favorite Sports Card -->
          <div class="card text-white bg-secondary shadow-sm animated-card">
            <div class="card-body">
              <h5 class="card-title">Favorite Sports</h5>
              <p class="card-text">I enjoy playing basketball and volleyball.</p>
              <i class="bi bi-basketball card-icon"></i>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer -->
    <AppFooter />
  </div>
</template>

<script>
import AppNavbar from '@/components/AppNavbar.vue';
import AppSidebar from '@/components/AppSidebar.vue';
import AppFooter from '@/components/AppFooter.vue';

export default {
  name: 'AboutMePage',
  components: {
    AppNavbar,
    AppSidebar,
    AppFooter,
  },
};
</script>

<style scoped>
.video-background {
  position: fixed; /* Fixed positioning to fill the screen */
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover; /* Cover the entire background */
  z-index: -1; /* Place the video behind other content */
}

.content {
  margin-top: 0;   /* Adjusted to match navbar height */
  height: calc(100vh - 60px); /* Ensure the content area takes full height minus navbar */
  overflow-y: auto; /* Allow vertical scrolling */
  display: flex; /* Enable Flexbox */
  justify-content: center; /* Center horizontally */
  align-items: center; /* Center vertically */
}

.about-me-container {
  display: flex;
  justify-content: center; /* Center the content horizontally */
  align-items: flex-start; /* Align content towards the top */
  flex-direction: column;
  text-align: center; /* Center text within cards */
}

.title {
  font-size: 2.8rem;
  color: #fff; /* Change text color to ensure visibility on video */
  margin-bottom: 10px;
  animation: fadeInTitle 1.5s ease-in-out;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
  margin-top: 20px;
}

/* Card styling */
.card {
  position: relative;
  border-radius: 10px;
  overflow: hidden;
}

.card-icon {
  position: absolute;
  top: 10px;
  right: 15px;
  font-size: 2rem;
  opacity: 0.3;
}

.card-title {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

.card-text {
  font-size: 1rem;
  line-height: 1.5;
}

/* Animations */
@keyframes fadeInTitle {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animated-card {
  animation: fadeInCard 1.5s ease-in-out;
  opacity: 1; /* Make sure it stays visible after the animation */
}

@keyframes fadeInCard {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

/* Media query for responsiveness */
@media (max-width: 768px) {
  .card-grid {
    grid-template-columns: 1fr; /* Stack cards on small screens */
  }
}
</style>
