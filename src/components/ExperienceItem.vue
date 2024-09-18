<template>
  <div class="grid grid-cols-[auto,1fr,auto] items-center gap-5 p-4 rounded-lg bg-white mt-2 shadow-md" @click="toggleDescription" >
    <img :src="logo" alt="Company logo" class="w-12 h-12 object-contain">

    <div class="flex flex-col">
      <div class="font-semibold text-lg">{{ title }}</div>
      <div class="text-sm text-gray-500">{{ dates }}</div>
    </div>

    <span v-if="$slots.default" class="cursor-pointer text-xl select-none">
      {{ isExpanded ? '▲' : '▼' }}
    </span>

    <div v-if="isExpanded" class="col-span-full text-gray-800 text-sm mt-2">
      <slot/>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: ['logo', 'title', 'dates'],
  data() {
    return { isExpanded: false }
  },
  methods: {
    toggleDescription() {
      if (this.$slots.default) {
        this.isExpanded = !this.isExpanded;
      }
    }
  }
}
</script>