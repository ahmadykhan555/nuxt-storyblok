<template>
  <header class="main-header left-0 top-0 w-full fixed h-16">
    <nav class="main-nav h-full">
      <ul
        class="
          nav-links
          h-full
          list-none
          flex
          p-0
          m-0
          justify-center
          align-middle
        "
      >
        <nuxt-link
          tag="li"
          class="h-full flex justify-center align-middle m-4 p-2"
          to="/"
          ><a class="block text-white hover:text-green-600">All posts</a>
        </nuxt-link>
        <nuxt-link
          tag="li"
          class="h-full flex justify-center align-middle m-4 p-2"
          to="/about"
          ><a class="block text-white hover:text-green-600">About Us</a>
        </nuxt-link>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
.main-header {
  background: #022d30;
}

.nuxt-link-exact-active a {
  color: rgba(5, 150, 105, 1);
  border-bottom: 3px solid #06c4d1;
}
</style>