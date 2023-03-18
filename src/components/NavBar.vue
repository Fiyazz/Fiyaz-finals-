<template>
  <nav class="flex md:flex-auto justify-between items-center font-serif bg-deepblue p-4">
    <div class="flex flex-row gap-2">
      <h3 class="text-2xl uppercase text-white">fiyazz</h3>
    </div>

    <!-- Hamburger Menu Button -->
    <button
      class="block md:hidden text-white hover:text-white focus:text-black focus:outline-none"
      @click="showMenu = !showMenu"
    >
      <svg
        class="h-6 w-6 fill-current"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          v-if="showMenu"
          d="M4 6h16M4 12h16M4 18h16"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
        <path
          v-else
          d="M4 6h16M4 12h16M4 18h16"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </button>

    <ul
      :class="[
        'flex',
        'md:flex',
        'md:flex-row',
        'flex-col',
        'gap-5',
        'justify-between',
        { hidden: !showMenu },
      ]"
    >
      <li class="text-white text-xl p-3 hover:text-white" id="home">
        <router-link to="/">{{ Home }}</router-link>
      </li>
      <li class="text-white text-xl p-3 hover:text-white" id="product">
        <router-link to="/productpage">{{ Products }}</router-link>
      </li>
      <li class="text-white text-xl hover:text-white" id="login">
        <router-link to="/login">{{ Login }}</router-link>
      </li>
      <li class="text-white text-xl hover:text-white" id="signup">
        <router-link to="/signup">{{ Signup }}</router-link>
      </li>
      <li class="text-white text-xl hover:text-white border-white border-2 p-3 rounded-xl" id="logout">
        <button @click="logout">{{ Logout }}</button>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      showMenu: false,
      Home: "Home",
      Products: "Products",
      Logout: "Log Out",
    };
  },
  created() {
    this.navbar();
  },
  methods: {
    logout() {
      localStorage.setItem("isAuthenticated", "false");
      location.reload();
      location.href("/login");
    },
    navbar() {
      if (localStorage.getItem("isAuthenticated") === "true") {
        (this.Login = ""),
          (this.Signup = ""),
          (this.Home = "Home"),
          (this.Products = "Products"),
          (this.Logout = "Log Out");
      } else {
        (this.Home = ""),
          (this.Products = ""),
          (this.Login = "Login"),
          (this.Signup = "Sign Up"),
          (this.Logout = "");
      }
    },
  },
};
</script>
<style scoped></style>
