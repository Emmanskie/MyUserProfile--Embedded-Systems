<template>
  <div class="video-background">
    <video autoplay muted loop class="background-video">
      <source src="@/assets/bg-profile.mp4" type="video/mp4" />
      Your browser does not support the video tag.
    </video>
    <div class="container">
      <h2 class="projects-title animated-title">My Projects</h2>
      <div class="row justify-content-center">
        <div class="col-md-4" v-for="project in projects" :key="project.id">
          <div class="card animated-card">
            <img :src="project.image" class="card-img-top" alt="Project Image">
            <div class="card-body">
              <h5 class="card-title animated-title">{{ project.title }}</h5>
              <p class="card-text animated-text">{{ project.description }}</p>
              <a :href="project.link" class="btn btn-primary animated-button" target="_blank" rel="noopener noreferrer">View Project</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PortfolioPage",
  data() {
    return {
      projects: [
        { id: 1, title: "Project 1", description: "I am one of the developers for this website.", image: require('@/assets/sdd.png'), link: "https://www.sddph.net/" },
      ],
    };
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
}

.projects-title {
  color: white; /* Change font color to white */
  text-align: center; /* Center the title */
  margin-bottom: 20px; /* Space between title and cards */
}

/* New Animations */
.animated-title {
  opacity: 0; /* Initial state */
  transform: translateY(-20px); /* Start slightly above */
  animation: fadeInUp 0.8s forwards; /* Animation details */
}

.animated-card {
  opacity: 0; /* Initial state */
  transform: translateY(20px); /* Start slightly below */
  animation: fadeInUp 0.6s forwards; /* Animation details */
}

.animated-text {
  opacity: 0; /* Initial state */
  transform: translateY(10px); /* Start slightly below */
  animation: fadeInUp 0.6s forwards; /* Animation details */
}

.animated-button {
  opacity: 0; /* Initial state */
  transform: scale(0.8); /* Start scaled down */
  animation: scaleUp 0.4s forwards; /* Animation details */
}

/* Keyframes for animations */
@keyframes fadeInUp {
  to {
    opacity: 1; /* End state */
    transform: translateY(0); /* End position */
  }
}

@keyframes scaleUp {
  to {
    opacity: 1; /* End state */
    transform: scale(1); /* End scale */
  }
}

.card-img-top {
  height: 200px;
  object-fit: cover;
}
</style>
