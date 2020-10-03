<template>
  <div class="flex flex-col min-h-screen bg-gray-100">
    <Navigation />
    <main class="container flex-grow p-6 mx-auto">
      <Nuxt />
    </main>
    <footer
      class="px-6 py-2 text-gray-800 bg-white border-t-2 border-gray-300 border-solid"
    >
      Copyright 2020
    </footer>
  </div>
</template>

<style>
.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
