<script lang="ts">
export default {
  data() {
  return {
    isMenuVisible: false,
    jobs: [
      {
        logo: '/Monzo-Emblem.png', // Company logo
        title: 'Technical Lead / Senior Software Engineer II at Monzo Bank', // Job title
        dates: 'Mar 2021 - present', // Employment dates
        description: 'Notable achievements:\n' +
            '* launched a new Customer Risk Assessment system, allowing Monzo to assess risky customers more\n' +
            'accurately. This resulted in a decrease in signup rejection rates and better identification of bad actors.\n' +
            '* launched a new Sanction Screening system, allowing the bank to start accepting incoming\n' +
            'international payments\n' +
            '* expanded and matured Transaction Monitoring system, to prevent and detect even more types of\n' +
            'crime in real-time and to achieve compliance with regulations\n' +
            'Recent highlights:\n' +
            '* prevented >£100K in money laundering losses, by introducing a control that automatically flags\n' +
            'complex cases for Senior Financial Crime Investigators\n' +
            '* reduced the operational cost of running the Transaction Monitoring system by >£175K/year, through\n' +
            'optimizations to the backend code\n' +
            'I\'ve been Senior Software', // Job description
        isExpanded: false, // State to track if description is expanded
      },
      {
        logo: '/ocado.png',
        title: 'Principal Software Engineer at Ocado Technology',
        dates: 'Mar 2014 - Feb 2021',
        description: 'I was a member of the Data Platform and Machine Learning Services teams. Together we:\n' +
            '* cut the storage and processing cost at least 5 times, by migrating analytical data and associated\n' +
            'workflows from Oracle to the GCP cloud\n' +
            '* improved quality and availability of data, by driving a cultural change in the organization to treat data\n' +
            'as a first-class citizen\n' +
            '\n' +
            'Przemysław Pastuszka - page 1\n' +
            '\n' +
            '* decreased lead time for data / ML projects by at least the factor of 4, by applying improvements and\n' +
            'automation to the entire process - starting from data exploration to deployment and monitoring\n' +
            'I was Senior Software Engineer at the beginning, but then gradually moved to being Team Leader and\n' +
            'then Principal Software Engineer.',
        isExpanded: false,
      },
      {
        logo: '/hadapt.png',
        title: 'Software Engineer at Hadapt',
        dates: 'Sep 2011 - Dec 2013',
        description: 'I worked on the proprietary distributed storage system (similar to HDFS).',
        isExpanded: false,
      },
    ],

  }
},
  methods: {
    toggleMenu() {
      this.isMenuVisible = !this.isMenuVisible;
    },
    toggleDescription(index) {
      this.jobs[index].isExpanded = !this.jobs[index].isExpanded; // Toggle the expanded state
    }
  },
}
</script>

<template>
  <nav>
    <div class="container">
      <h1 class="logo">Przemek Pastuszka</h1>
      <ul v-bind:class="{ show: isMenuVisible }" id="nav-list">
        <li><a href="#about" @click="toggleMenu">About</a></li>
        <li><a href="#experience" @click="toggleMenu">Experience</a></li>
        <li><a href="#education" @click="toggleMenu">Education</a></li>
        <li><a href="#contact" @click="toggleMenu">Contact</a></li>
      </ul>
      <span class="mobile-nav-toggle" @click="toggleMenu">&#9776;</span>
    </div>
  </nav>


  <!-- Hero Section -->
  <section class="hero" id="about">
    <div class="container">
      <div class="content">
        <h2>Welcome to my personal website</h2>
        <p>I'm a <b>product-oriented engineer</b>, caring deeply about business metrics and leveraging data to
          inform the decision-making process.</p>

        <p>I'm <b>seasoned in delivering complex projects</b>, where requirements are ambiguous and multiple stakeholders
          often
          pursue different objectives</p>
        <p> I always try to be very intentional and pragmatic about delivering for the short vs. long term; shifting
          gears between strategic and
          tactical thinking as needed.</p>
      </div>
      <div class="image">
        <img src="https://via.placeholder.com/500x300" alt="Placeholder Image">
      </div>
    </div>
  </section>

  <!-- Features Section -->
  <section class="work-experience" id="experience">
    <div class="container">
      <h2>Work experience</h2>
      <div
          class="job-entry"
          v-for="(job, index) in jobs"
          :key="index"
          :class="{ expanded: job.isExpanded }"
      >
        <!-- Company Logo -->
        <img :src="job.logo" alt="Company logo">

        <!-- Job Details (title and dates) -->
        <div class="job-details">
          <div class="job-title">{{ job.title }}</div>
          <div class="job-dates">{{ job.dates }}</div>
        </div>

        <!-- Down Arrow for expanding -->
        <span class="down-arrow" @click="toggleDescription(index)">
        {{ job.isExpanded ? '▲' : '▼' }}
      </span>

        <!-- Job Description (toggle visibility) -->
        <div class="job-description">
          {{ job.description }}
        </div>
      </div>
    </div>
  </section>

  <!-- Features Section -->
  <section id="education" class="features">
    <div class="container">
      <h2>Education</h2>
      <div class="feature">
        <h3>Feature 1</h3>
        <p>Aliquam tincidunt mauris eu risus. Vivamus vestibulum nisl eget ipsum volutpat vel pretium metus
          condimentum.</p>
      </div>
      <div class="feature">
        <h3>Feature 2</h3>
        <p>Phasellus lacinia metus eget erat condimentum, id gravida ex cursus. Nulla facilisi. Nullam scelerisque
          turpis sit amet.</p>
      </div>
      <div class="feature">
        <h3>Feature 3</h3>
        <p>Fusce condimentum fermentum nunc. Etiam pharetra, erat sed fermentum feugiat, velit mauris egestas
          quam.</p>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <p>© 2024 Przemek Pastuszka. All Rights Reserved.</p>
  </footer>
</template>

<style scoped>
/* Navigation Styles */
nav {
  background-color: #ffffff;
  padding: 20px 0;
  position: sticky;
  top: 0;
  width: 100%;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  z-index: 999;
}

nav .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 20px;
}

nav ul li {
  position: relative;
}

nav ul li:hover {
  background-color: #f4f4f9;
}

nav ul li a {
  text-decoration: none;
  font-size: 1.1rem;
  color: #333;
  text-transform: uppercase;
  font-weight: 500;
  transition: color 0.3s ease;
}

/* Mobile Navigation Toggle (Hamburger Menu) */
.mobile-nav-toggle {
  display: none;
  font-size: 1.8rem;
  cursor: pointer;
}


/* Hero Section */
.hero {
  background: #f4f4f9;
  padding: 50px 20px;
  display: flex;
  flex-wrap: wrap;
}

.hero .content {
  flex: 1;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.hero h2 {
  font-size: 2rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 20px;
}

.hero p {
  font-size: 1.1rem;
  color: #666;
  margin-bottom: 30px;
  line-height: 1.8;
  text-align: justify;
  text-justify: inter-word;
}

.hero .image {
  flex: 1;
  text-align: center;
}

.hero .image img {
  max-width: 100%;
  height: auto;
}

/* Features Section */
.features {
  padding: 10px 20px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.feature {
  background: white;
  padding: 30px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  transition: transform 0.3s ease;
  margin-top: 10px;
}

.feature h3 {
  font-size: 1.5rem;
  margin-bottom: 15px;
  color: #4a90e2;
}

.feature p {
  font-size: 1rem;
  color: #666;
}

.work-experience {
  padding: 10px 20px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

/* Ensure each job entry is neatly aligned */
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
  margin-top: 10px;
  font-size: 0.9rem;
  color: #333;
  padding: 10px;
  border-radius: 5px;
}

/* Show the description when expanded */
.expanded .job-description {
  display: block;
}

/* Footer */
footer {
  background-color: #333;
  color: #fff;
  padding: 20px 0;
  text-align: center;
  margin-top: 50px;
}

footer p {
  font-size: 0.9rem;
}

/* Media Queries for Mobile Responsiveness */
@media (max-width: 768px) {
  nav ul {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 80px;
    left: 0;
    width: 100%;
    background-color: #fff;
    text-align: center;
  }

  nav ul.show {
    display: flex;
  }

  .mobile-nav-toggle {
    display: block;
    color: #333;
  }

  .hero {
    flex-direction: column;
  }

  .hero .content {
    padding-right: 0;
  }
}
</style>
