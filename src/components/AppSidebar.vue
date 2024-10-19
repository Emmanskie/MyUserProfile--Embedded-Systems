<template>
  <div
    id="sidebar-wrapper"
    :class="{ collapsed: isCollapsed }"
    @mouseover="toggleSidebar(false)"
    @mouseleave="toggleSidebar(true)"
  >
    <div class="sidebar-content">
      <ul class="list-group">
        <li class="list-group-item" :class="{ active: isActive('DashboardHome') }" @click="navigateTo('dashboard/home')">
          <i class="fas fa-home"></i> Home
        </li>
        <li class="list-group-item" :class="{ active: isActive('AboutMePage') }" @click="navigateTo('dashboard/aboutme')">
          <i class="fas fa-user"></i> About Me
        </li>
        <li class="list-group-item" :class="{ active: isActive('Profile') }" @click="navigateTo('dashboard/profile')">
          <i class="fas fa-user"></i> Profile
        </li>
      </ul>
      <div class="flex-grow-1"></div>
      <div class="logout-container">
        <button class="btn btn-outline-dark w-100" @click="handleLogout">Logout</button>
      </div>
    </div>
  </div>
</template>

<script>
import { useRouter } from 'vue-router';

export default {
  name: "AppSidebar",
  data() {
    return {
      isCollapsed: true,
    };
  },
  setup() {
    const router = useRouter();
    return { router };
  },
  methods: {
    toggleSidebar(state) {
      this.isCollapsed = state;
    },
    isActive(routeName) {
      return this.$route.name === routeName;
    },
    navigateTo(route) {
      this.$router.push(`/${route}`);
    },
    handleLogout() {
      this.router.push('/'); 
    }
  },
};
</script>

<style scoped>
#sidebar-wrapper {
  width: 250px;
  display: flex;
  flex-direction: column;
  background-image: url("@/assets/side-bg.png"); 
  background-size: cover; 
  background-position: center; 
  position: fixed;
  left: 0;
  top: 0;
  height: 100%;
  transition: width 0.3s ease; 
  z-index: 1; 
  box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1); 
  overflow: hidden; 
}

#sidebar-wrapper.collapsed {
  width: 60px; 
}

.sidebar-content {
  display: flex;
  flex-direction: column;
  height: 100%;
  padding: 40px;
  margin-top: 20px; 
}

.list-group-item {
  border: none;
  color: white; 
  background-color: transparent; 
  padding: 15px;
  cursor: pointer;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  display: flex;
  align-items: center;
  transition: background-color 0.3s; 
}

.list-group-item i {
  margin-right: 10px; 
}

.list-group-item.active {
  background-color: rgba(255, 255, 255, 0.2); 
  color: #007bff; 
}

.list-group-item:hover {
  background-color: rgba(255, 255, 255, 0.3); 
  color: #007bff; 
}

.flex-grow-1 {
  flex-grow: 1;
}

.logout-container {
  padding-top: 20px; 
}

.btn-outline-dark {
  color: white; 
  border-color: white; 
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis; 
}

.btn-outline-dark:hover {
  background-color: rgba(156, 17, 17, 0.2); 
  color: rgb(194, 34, 34); 
}
</style>
