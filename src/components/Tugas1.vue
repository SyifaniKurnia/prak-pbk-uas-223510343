<template>
  <div>
    <section class="home" id="home">
      <main class="content">
        <h1>Hello, <span> I am </span> Syifani!</h1>
        <p>
          Bagi saya, kesederhanaan adalah inti dari seni. Semua hal tentang
          minimalis dan estetika.
        </p>
        <a href="#" class="cta">Hire Me!</a>
      </main>
    </section>
  </div>
</template>

<style scoped>
h1 {
  font-family: "Radley";
  color: #000;
}

.home {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  background-color: #f4f1e8;
}

.home .content {
  padding: 1.4rem 7%;
  max-width: 60rem;
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(3, auto);
  align-items: center;
  text-align: center;
}

.home .content h1 {
  font-size: 4.5em;
  line-height: 1.2;
  text-align: center;
}

.home .content h1 span {
  color: #9b4814;
}

.home .content p {
  font-size: 2rem;
  margin-top: 1rem;
  line-height: 1.4;
  font-weight: 300;
  text-align: center;
}

.cta {
  margin: 0 auto;
  margin-top: 3rem;
  display: inline-block;
  padding: 0.5rem 1.5rem;
  font-size: 1.4rem;
  color: #fff;
  background-color: #9b4814;
  border-radius: 0.5rem;
  font-family: "Radley";
  font-style: italic;
  max-width: 12rem;
  text-decoration: none;
  text-align: center;
  line-height: 2;
}
</style>
