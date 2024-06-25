<template>
  <div id="app">
    <q-layout view="hHh lpR fFf">
      <q-header elevated class="app-navbar">
        <div class="toolbar">
          <q-toolbar-title
            class="q-pa-md"
            style="font-weight: bold; font-size: 1.6rem"
            >Syifani_343</q-toolbar-title
          >
          <div class="link">
            <button class="q-btn" @click="goto('')">Weather</button>
            <button class="q-btn" @click="goto('tugas1')">Tugas 1</button>
            <button class="q-btn" @click="goto('tugas2')">Tugas 2</button>
            <button class="q-btn" @click="goto('tugas3')">Tugas 3</button>
            <button class="q-btn" @click="goto('tugas4')">Tugas 4</button>
            <button class="q-btn" @click="goto('tugas5')">Tugas 5</button>
            <button class="q-btn" @click="goto('tugas6')">Tugas 6</button>
            
            <div class="dropdown q-mr-sm">
              <button class="q-btn">Link Web Tugas</button>
              <div class="dropdown-content">
                <a
                  href="https://syifani-project-cv.netlify.app/
"
                  >Link Tugas 1</a
                >
                <a
                  href="https://github.com/SyifaniKurnia/223510343_Tugas2
"
                  >Link Tugas 2</a
                >
                <a
                  href="https://223510343-syifani.netlify.app
"
                  >Link Tugas 3</a
                >
                <a
                  href="https://github.com/SyifaniKurnia/Syifani_Parking
"
                  >Link Tugas 4</a
                >
                <a href="https://syifani-223510343.netlify.app/"
                  >Link Tugas 6</a
                >
              </div>
            </div>
          </div>
        </div>
      </q-header>
      <q-page-container>
        <router-view />
      </q-page-container>
    </q-layout>
  </div>
</template>

<script>
export default {
  name: "App",
  methods: {
    goto(page) {
      this.$router.push(`/${page}`);
    },
  },
};
</script>

<style scoped>
#app {
  background-color: #77b0aa;
}
.app-navbar {
  background-color: #003c43;
  color: white;
  padding: 1rem 2rem;
}

.toolbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.link {
  display: flex;
  align-items: center;
}

.app-navbar .q-btn {
  display: flex;
  align-items: center;
  padding: 5px 15px;
  color: #003c43;
  font-size: 1.3rem;
  font-weight: 800;
  margin-left: 1rem;
  transition: text-decoration 0.3s ease;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
  background-color: aliceblue;
}

.app-navbar .q-btn:hover {
  text-decoration: underline;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.q-btn {
  background-color: purple;
  color: white;
  padding: 8px 16px;
  font-size: 16px;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
  border-radius: 4px;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {
  background-color: #f1f1f1;
}

.dropdown:hover .dropdown-content {
  display: block;
}

.dropdown:hover .q-btn {
  background-color: #0b4b52;
}
</style>
