<template>
  <div class="video-bg-container">
    <!-- Video Background -->
    <video autoplay muted loop id="bg-video">
      <source src="@/assets/bg2.mp4" type="video/mp4" />
      Your browser does not support the video tag.
    </video>

    <div class="container">
      <h2 class="fade-in">Student Profile</h2>
      <div class="profile-content fade-in">
        <img src="@/assets/rioyan_id.jpg" alt="Profile Picture" class="profile-img" />
        <p>
          Hi, I am Jose Emmanuel Rioyan, a passionate and resilient student.
          Flexible and hardworking team player focused on boosting productivity and performance with conscientious and detail-oriented approaches.
          Resourceful team player with experience with common software applications and social media platforms.
          Well-versed in organization and strategies for successfully modernizing workplaces.
          Skilled at project support with a proven history of solutions-oriented problem-solving.
        </p>
      </div>

      <div class="details fade-in">
        <h3>Education</h3>
        <p>
          Technological Institute of the Philippines 
          <br />
          Bachelor of Science in Computer Engineering (Expected Graduation: 2025)
        </p>
        <ul>
          <li>Vice President's Lister Second Semester (2021 - 2022)</li>
          <li>Vice President's Lister First Semester (2022 - 2023)</li>
          <li>Vice President's Lister Second Semester (2022 - 2023)</li>
          <li>Deans's Lister First Semester (2023 - 2024)</li>
          <li>Vice President's Lister Second Semester (2023 - 2024)</li>
          <li>Web Development: HTML, CSS, Vue.js, Node.js</li>
          <li>Flexibility, Interpersonal Skills, Creativity, Resilience, Conflict Resolution, Curiosity</li>
          <li>Code Development, IoT Development, Software Development, AutoCAD, Debugging</li>
        </ul>

        <h3>Organizational Experience</h3>
        <ul>
          <li>Science Club - Member (2015 - 2021)</li>
          <li>Computer Engineering Student Society - Member (2022 - Present)</li>
          <li>Computer Engineering Student Society - Creatives Committee (2023)</li>
          <li>Institute of Computer Engineering of the Philippines - Member (2022 - Present)</li>
        </ul>

        <h3>Skills</h3>
        <ul>
          <li>Programming Languages: JavaScript, Python, C++</li>
          <li>Web Development: HTML, CSS, Vue.js, Node.js</li>
          <li>Flexibility, Interpersonal Skills, Creativity, Resilience, Conflict Resolution, Curiosity</li>
          <li>Code Development, IoT Development, Software Development, AutoCAD, Debugging</li>
        </ul>

        
        <h3>Certificates</h3>
        <ul>
          <li>Cisco Course Completion Certificates</li>
          <li>Capture the Flag National Competition Certificate of Participation</li>
          <li>Academic Merit Certificates</li>
        </ul>

        <h3>Extracurricular Activities</h3>
        <p>
          Involvement in various clubs and organizations that enhance my skills and network:
        </p>
        <ul>
          <li>Participant in spelling bee competitions (2013 - 2015)</li>
          <li>Member of the Boy Scouts of the Philippines (2015)</li>
          <li>Volunteer for community service projects</li>
          <li>Participant in Capture the Flag competitions (2024)</li>
        </ul>

        <h3>Seminars Joined</h3>
        <ul>
          <li>IoT in Agriculture Workshop 2022</li>
          <li>Tech Innovations Seminar 2023</li>
          <li>Programming Best Practices Webinar 2023</li>
          <li>CyberAware Seminar 2024</li>
        </ul>
      </div>

      <!-- Social Media Links -->
      <div class="social-media">
        <h3>Connect with Me</h3>
        <a href="https://www.facebook.com/Emman.Rioyan.me" target="_blank" class="social-link">
          <img src="@/assets/facebook-icon.png" alt="Facebook" />
        </a>
        <a href="https://www.instagram.com/emmanskieeeeeee/" target="_blank" class="social-link">
          <img src="@/assets/instagram-icon.png" alt="Instagram" />
        </a>
        <a href="linkedin.com/in/jose-emmanuel-rioyan-2648ab22a" target="_blank" class="social-link">
          <img src="@/assets/linkedin-icon.png" alt="LinkedIn" />
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProfilePage",
};
</script>

<style scoped>
/* Video Background */
#bg-video {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  object-fit: cover;
  z-index: -1;
  opacity: 0.8;
}

/* Container styles */
.container {
  position: relative; /* Ensure content is layered above the video */
  z-index: 1;
  padding: 20px;
  margin-left: 80px;
  margin-bottom: 50px;
  font-family: 'Arial', sans-serif;
  font-size: 1.1rem;
}

.profile-content {
  display: flex;
  align-items: center;
}

.profile-img {
  width: 150px;
  border-radius: 50%;
  margin-right: 20px;
}

.details {
  margin-top: 20px;
  margin-bottom: 50px;
}

h2 {
  font-size: 2rem;
}

h3 {
  margin-top: 10px;
  font-size: 1.5rem;
}

p, li {
  font-size: 1.2rem;
}

/* Social Media Links */
.social-media {
  margin-top: 30px;
  text-align: center;
}

.social-media h3 {
  margin-bottom: 30px;
  font-size: 1.5rem;
}

.social-link {
  margin: 0 10px;
}

.social-link img {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  transition: transform 0.3s ease;
}

.social-link img:hover {
  transform: scale(1.2);
}

/* Fade-in animation */
.fade-in {
  animation: fadeIn 1s ease-in-out forwards;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
