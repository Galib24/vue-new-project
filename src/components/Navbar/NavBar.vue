<script setup>
import './NavBar.css'
</script>

<template>
    <div class="navbar">
      <div class="left-section">
        <div class="logo">
          <span class="pink">movie</span><span class="blue">box</span><span class="admin">Admin</span>
        </div>
        <nav class="nav-links">
          <a href="#" class="active">Overview</a>
          <a href="#">Movies</a>
          <a href="#">Upload</a>
          <a href="#">Reporting</a>
          <a href="#">Users</a>
        </nav>
      </div>
  
      <div class="icons">
        <span class="icon">⚙️</span>
        <svg class="icon notification" xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="white" viewBox="0 0 24 24">
        <path d="M12 24c1.104 0 2-.896 2-2h-4c0 1.104.896 2 2 2zm6-6v-5c0-3.072-1.639-5.641-4.5-6.32V6c0-.828-.671-1.5-1.5-1.5S10.5 5.172 10.5 6v.68C7.639 7.359 6 9.928 6 13v5l-2 2v1h16v-1l-2-2z"/>
      </svg>
        <img class="avatar" src="https://i.pravatar.cc/30" alt="User" />
      </div>
    </div>
  </template>
  
 