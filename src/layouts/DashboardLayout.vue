<template>
  <div>
    <AppNavbar />
    <AppSidebar />
    <div class="content">
      <h1 v-if="isDashboardHome" class="fade-in">Welcome to my User Profile!</h1>
      <p v-if="isDashboardHome" class="fade-in">Here you can see some statistical reports during my college journey!</p>
      
      <div v-if="isDashboardHome" class="stats fade-in">
        <div class="stat">
          <h3>Total Freelance Projects Completed</h3>
          <p>1</p>
        </div>
        <div class="stat">
          <h3>Programming Languages Proficient In</h3>
          <p>3</p>
        </div>
        <div class="stat">
          <h3>Certifications Earned</h3>
          <p>6</p>
        </div>
        <div class="stat">
          <h3>Cybersecurity Events Attended</h3>
          <p>3</p>
        </div>
      </div>
      
      <blockquote v-if="isDashboardHome" class="fade-in">
        "Success is not the key to happiness. Happiness is the key to success. If you love what you are doing, you will be successful." 
      </blockquote>
      
      <router-view />
    </div>
    <AppFooter />
  </div>
</template>

<script>
import AppNavbar from '@/components/AppNavbar.vue';
import AppSidebar from '@/components/AppSidebar.vue';
import AppFooter from '@/components/AppFooter.vue';

export default {
  name: 'DashboardLayout',
  components: {
    AppNavbar,
    AppSidebar,
    AppFooter,
  },
  computed: {
    isDashboardHome() {
      return this.$route.name === 'Home'; 
    },
  },
};
</script>

<style scoped>
.content {
  margin-left: 60px; 
  margin-top: 50px; 
  padding: 0; 
  height: calc(100vh - 60px); 
  overflow-y: auto; 
  transition: margin-left 0.3s ease; 
}

h1 {
  font-size: 2rem;
  margin-bottom: 10px;
}

p {
  margin-bottom: 20px;
}

.stats {
  display: flex;
  flex-wrap: wrap; 
  justify-content: space-around; 
  margin: 20px 0; 
}

.stat {
  background: #e9ecef; 
  padding: 10px;
  border-radius: 8px;
  text-align: center;
  width: 45%; 
  margin: 10px; 
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1); 
}

blockquote {
  font-style: italic;
  color: #555; 
  border-left: 4px solid #007bff; 
  padding-left: 10px;
  margin: 20px 0; 
}

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
