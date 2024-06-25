<template>
  <div>
    <nav class="navbar">
      <router-link to="/" class="navbar-logo">
        <span>Syifani_343</span>
      </router-link>

      <div class="navbar-links">
        <router-link to="/" class="navbar-link">Weather</router-link>
        <router-link to="/tugas1" class="navbar-link">Tugas</router-link>
      </div>
    </nav>
  </div>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.4rem 7%;
  background-color: #003c43;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 9999;
  width: 100%;
}

.navbar .navbar-logo {
  font-size: 2rem;
  color: #fff;
  text-decoration: none;
}

.navbar .navbar-logo span {
  font-weight: bold;
}

.navbar .navbar-links {
  display: flex;
  align-items: center;
}

.navbar .navbar-link {
  padding: 10px 20px;
  color: #fff;
  font-size: 1.2rem;
  font-weight: 600;
  text-decoration: none;
  margin-left: 2rem;
  border-radius: 20px;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.navbar .navbar-link:hover {
  background-color: #fff;
  color: #003c43;
}
</style>
