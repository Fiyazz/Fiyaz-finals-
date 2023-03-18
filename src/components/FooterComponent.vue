<template>
  <div class="flex flex-row gap-20 justify-between bg-black font-serif text-white p-8 text-center">
    <div class="flex flex-row gap-2">
      <p class="text-2xl uppercase">fiyazz</p>
    </div>

    <ul class="flex flex-row justify-between gap-10">
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/productpage">Shop</router-link></li>
    </ul>

    <p class="copy">All rights reserved. © 2023 <span class="uppercase">fiyazz</span>.</p>
  </div>
</template>

<script>
export default {
  name: "FooterComponent",
};
</script>
