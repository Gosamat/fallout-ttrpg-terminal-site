<template>
  <div class="old-crt-monitor">
    <div class="retro-container scanline-effect">
      <header>
        <h1>Fallout TTRPG Terminal</h1>
        <nav role="navigation">
          <ul>
            <li><a href="#screen-1" @click.prevent="scrollToSection">Dwellers</a></li>
            <li><a href="#screen-1" @click.prevent="scrollToSection">Vaults</a></li>
            <li><a href="#screen-1" @click.prevent="scrollToSection">Login/SignUp</a></li>
          </ul>
        </nav>
      </header>
      <main ref="main">
        <section id="screen-1">
          <article>
            <header>
              <h2>Dwellers</h2>
            </header>
            <div class="content">This is the Dwellers page</div>
            <figure>
              <img src="" alt="alt text for illustration" />
            </figure>
          </article>
        </section>
      </main>
      <footer>
        <p>
          @2024 Fallout TTRPG Terminal is a small project I'm making so me and my friends can have a
          website to use for our Fallout TTRPG sessions. It's a work in progress, but I'm having fun
          making it.
        </p>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RetroUI',
  methods: {
    scrollToSection(event) {
      const targetId = event.target.getAttribute('href')
      const targetElement = document.querySelector(targetId)
      const main = this.$refs.main

      if (targetElement) {
        main.scrollTo({
          top: targetElement.offsetTop - main.offsetTop,
          behavior: 'smooth'
        })
      }
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');

* {
  scrollbar-color: var(--primary-color) var(--secondary-color);
  font-size: clamp(18px, 3vw, 30px);
  font-family: 'VT323', monospace;
  font-weight: 400;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

ul {
  list-style: none;
  display: flex;

  li {
    margin: 1rem;
  }
}

h1,
h2 {
  font-weight: bold;
}

body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: var(--background-color);
  color: var(--primary-color);
  cursor: url('./assets/mouse.svg');
}

.retro-container {
  height: 90vh;
  display: grid;
  grid-template-rows: auto 1fr auto;
  overflow: hidden;
  padding: 0.5rem;
  border: 2px solid var(--primary-color);
  color: var(--primary-color);
  mask-image: linear-gradient(to bottom, #0005 50%, #000 50%);
  mask-size: 100% 2px;
  text-shadow: 0 0 0.5rem;
}

a {
  color: inherit;
  text-decoration: none;
}

header,
footer {
  display: flex;
  gap: 2rem;
  justify-content: space-between;
  align-items: center;
}

main {
  overflow: hidden;
}

footer p {
  font-size: 24px;
}

section {
  height: 100%;
  overflow: hidden auto;
  margin: 1rem 0;
}

@keyframes crtAnimation {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: 0 10000%;
  }
}

.old-crt-monitor {
  box-shadow: inset 0px 0px 2rem;
  background-image: linear-gradient(0deg, #0000 10%, #fff1 90%, #0000 100%);
  animation: crtAnimation 100s linear infinite;
  background-size: 100% 80%;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
  background-color: var(--background-color);
  color: var(--primary-color); /* Set the text color */
  cursor: url('./assets/mouse.svg');
}

alert {
  animation: blink-bg 1s ease-out infinite;
}

@keyframes blink-bg {
  0%,
  60% {
    text-shadow: 0 0 10.5rem;
    color: var(--primary-color);
  }
  70%,
  100% {
    text-shadow: 0 0 20.5rem;
    color: var(--tertiary-color);
  }
}
</style>
