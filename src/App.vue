<template>
  <div class="relative">
    <div class="w-screen h-screen absolute top-0 left-0">
      <Particles
        id="particles"
        :particlesInit="particlesInit"
        :particlesLoaded="particlesLoaded"
        :options="particlesOptions"
      />
    </div>
    <div class="w-screen h-screen absolute top-0 left-0">
      <div class="container mx-auto px-6 h-screen flex flex-col">
        <div class="py-8 flex items-center justify-between text-[#f8ffe5]">
          <div class="flex items-center">
            <button class="flex items-center">
              <i class="ph-list text-2xl"></i>
            </button>
          </div>
          <nav class="flex items-center space-x-6">
            <router-link to="/">Home</router-link>
            <router-link to="/about">About</router-link>
          </nav>
          <div class="flex items-center">
            <button class="flex items-center">
              <i class="ph-magnifying-glass text-2xl"></i>
            </button>
          </div>
        </div>
        <router-view class="grow" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { loadFull } from "tsparticles";

const particlesInit = async (engine) => {
  await loadFull(engine);
};

const particlesLoaded = async (container) => {
  console.log("Particles container loaded", container);
};

const particlesOptions = {
  background: {
    color: "#071f36",
  },
  detectRetina: false,
  fpsLimit: 120,
  interactivity: {
    detectsOn: "canvas",
    events: {
      resize: true,
    },
  },
  particles: {
    color: {
      value: "#f8ffe5",
    },
    move: {
      angle: {
        offset: 45,
        value: 90,
      },
      direction: "top-right",
      enable: true,
      outModes: "out",
      random: false,
      speed: 2,
      straight: true,
    },
    number: {
      density: {
        enable: true,
        area: 800,
      },
      value: 80,
    },
    opacity: {
      animation: {
        enable: false,
      },
      value: {
        min: 0,
        max: 0.3,
      },
    },
    shape: {
      type: "circle",
    },
    size: {
      value: { min: 1, max: 3 },
    },
  },
};
</script>

<style>
#app {
  font-family: Montserrat, Tajawal, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f8ffe5;
  background-color: #071f36;
  min-height: 100vh;
}

nav a {
  font-weight: 500;
  color: #f8ffe5;
}

nav a.router-link-exact-active {
  color: #f8ffe5;
}
</style>
