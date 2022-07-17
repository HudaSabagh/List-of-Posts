<template>
  <div id="app ">
    <div id="nav" class="bg-red-500 shadow-lg flex flex-col lg:flex-row">
      <router-link
        to="/"
        class="text-white py-2 m-1 px-4 rounded-md"
        exact-active-class="bg-red-800"
        >Home</router-link
      >

      <router-link
        class="text-white py-2 m-1 px-4 rounded-md"
        exact-active-class="bg-red-800"
        to="/about"
        >About</router-link
      ><!-- rounded-md  medieum border radius for active class -->
    </div>
    <router-view />
  </div>
</template>

<style lnng="scss">
@font-face {
  font-family: "IBM Plex Mono", monospace;
  font-family: "Poppins", sans-serif;
  src: url("https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:ital,wght@0,100;0,200;0,700;1,100;1,200;1,300;1,400;1,600;1,700&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
}
#app {
  font-family: "IBM Plex Mono", monospace;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}
</style>
