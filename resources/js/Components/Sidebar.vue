<script>
import { TiThMenu } from 'vue-icons-plus/ti'
</script>
<template>
  <div :class="['sidebar', { collapsed: isCollapsed }]">
    <button class="toggle-btn" @click="toggleSidebar">
      <component :is="isCollapsed ? TiThMenu  : EpArrowLeftBold" class="icon" />
    </button>
    <ul v-if="!isCollapsed">
      <li class="p-2 hover:bg-gray-500 text-lg hover:text-gray-900 hover:font-semibold cursor-pointer">
        <inertia-link href="/dashboard">Dashboard</inertia-link>
      </li>
      <li class="p-2 hover:bg-gray-500 text-lg hover:text-gray-900 hover:font-semibold cursor-pointer">
        <inertia-link href="/animals">Manage Animals</inertia-link>
      </li>
      <li class="p-2 hover:bg-gray-500 text-lg hover:text-gray-900 hover:font-semibold cursor-pointer">
        <inertia-link href="/reports">Reports</inertia-link>
      </li>
      <li class="p-2 hover:bg-gray-500 text-lg hover:text-gray-900 hover:font-semibold cursor-pointer">
        <inertia-link href="/settings">Settings</inertia-link>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { EpArrowLeftBold, EpArrowRightBold } from "vue-icons-plus/ep";

const isCollapsed = ref(false);

const toggleSidebar = () => {
  isCollapsed.value = !isCollapsed.value;
};
</script>

<style scoped>
.sidebar {
  width: 250px;
  height: 100vh;
  background: #2c3950;
  color: white;
  padding: 20px;
  position: fixed;
  transition: width 0.3s ease;
}

.sidebar.collapsed {
  width: 60px;
  padding: 10px;
}


.toggle-btn {
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  position: absolute;
  right: -25px; 
  top: 3%;
  transform: translateY(-10%);
  padding: 5px 10px;
  border-radius: 50%;
  transition: all 0.3s ease;
}

.sidebar.collapsed .toggle-btn {
  right: auto;
  left: 50%; 
  transform: translate(-50%, -10%);
  color:white 
}

.toggle-btn .icon{
  color: azure;
}
.icon {
  width: 30px;
  height: 30px;
  color: #1f2d3d;
}

.icon:hover{
  color: white
}
</style>
