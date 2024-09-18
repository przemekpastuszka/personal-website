<template>
  <div class="job-entry" :class="{ expanded: isExpanded }">
    <img :src="logo" alt="Company logo">

    <div class="job-details">
      <div class="job-title">{{ title }}</div>
      <div class="job-dates">{{ dates }}</div>
    </div>

    <span class="down-arrow" @click="toggleDescription">
        {{ isExpanded ? '▲' : '▼' }}
      </span>

    <div class="job-description">
      <slot/>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: ['logo', 'title', 'dates'],
  data() {
    return {isExpanded: false}
  },
  methods: {
    toggleDescription() {
      this.isExpanded = !this.isExpanded;
    },
  }
}
</script>

<style scoped>
.job-entry {
  display: grid;
  grid-template-columns: auto 1fr auto auto;
  align-items: center;
  gap: 20px;
  padding: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  background-color: #fff;
  margin-top: 10px;
}

/* Center the logo, title, dates, and down arrow neatly */
.job-entry img {
  width: 50px;
  height: 50px;
  object-fit: contain;
}

.job-details {
  display: flex;
  flex-direction: column;
}

.job-title {
  font-size: 1.2rem;
  font-weight: 600;
}

.job-dates {
  font-size: 0.9rem;
  color: #666;
}

.down-arrow {
  cursor: pointer;
  font-size: 1.5rem;
  user-select: none;
}

/* Hidden job description initially */
.job-description {
  display: none;
  grid-column: 1 / -1; /* Span the description across all grid columns */
  font-size: 0.9rem;
  color: #333;
  padding: 10px;
}

.expanded .job-description {
  display: block;
}
</style>