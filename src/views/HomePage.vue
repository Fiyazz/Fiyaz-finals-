<template>
  <div>
    <NavBar />
    <div class="flex flex-col justify-center items-center h-screen main">
      <img
        src="../assets/header.png"
        alt="product one"
        class="relative w-full h-full"
      />
      <h1
        class="md:text-7xl text-4xl text-deepblue font-sans md:w-[750px] md:m-14 m-8 absolute z-10"
      >
        DISCOVER UNIQUE & AUTHENTIC GADGETS
      </h1>
      <button
        class="font-serif w-[170px] h-[60px] bg-deepblue text-grey absolute z-10 rounded-md md:mt-[300px] mt-[250px]"
      >
        <router-link to="/productpage"> Discover Now </router-link>
      </button>
    </div>
    <FooterComponent />
  </div>
</template>
<script>
import FooterComponent from "@/components/FooterComponent.vue";
import NavBar from "@/components/NavBar.vue";

export default {
  name: "HomePage",
  components: {
    NavBar,
    FooterComponent
},
};
</script>
