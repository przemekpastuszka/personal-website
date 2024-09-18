<template>
  <nav class="bg-white py-5 sticky top-0 w-full shadow-md z-50">
    <div class="container mx-auto flex justify-between items-center">
      <h1 class="text-2xl font-bold">Przemek Pastuszka</h1>
      <ul
          :class="{'flex': isMenuVisible, 'hidden': !isMenuVisible }"
          class="hidden md:flex space-x-8"
      >
        <li v-for="section in sections" :key="section">
          <a :href="'#' + section" @click="toggleMenu" class="text-gray-800 hover:text-blue-500 uppercase">{{ section }}</a>
        </li>
      </ul>

      <span
          class="md:hidden text-3xl cursor-pointer"
          @click="toggleMenu"
      >&#9776;</span>
    </div>

    <ul
        :class="{'block': isMenuVisible, 'hidden': !isMenuVisible }"
        class="md:hidden bg-white w-full text-center space-y-4 py-5"
    >
      <li v-for="section in sections" :key="section">
        <a :href="'#' + section" @click="toggleMenu" class="text-gray-800 hover:text-blue-500 block uppercase">{{ section }}</a>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
export default {
  data() {
    return {isMenuVisible: false, sections: ['about', 'experience', 'education']}
  },
  methods: {
    toggleMenu() {
      this.isMenuVisible = !this.isMenuVisible;
    },
  }
}
</script>

