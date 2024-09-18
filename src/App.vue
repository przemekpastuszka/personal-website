<script lang="ts">

import Footer from "@/components/Footer.vue";
import Navigation from "@/components/Navigation.vue";
import ExperienceSection from "@/components/ExperienceSection.vue";
import ExperienceItem from "@/components/ExperienceItem.vue";

export default {
  components: {
    ExperienceItem,
    ExperienceSection,
    Footer,
    Navigation,
  },
}
</script>

<template>
  <Navigation/>

  <section class="hero" id="about">
    <div class="container">
      <div class="content">
        <h2>Welcome to my personal website</h2>
        <p>I'm a <b>product-oriented engineer</b>, caring deeply about business metrics and leveraging data to
          inform the decision-making process.</p>

        <p>I'm <b>seasoned in delivering complex projects</b>, where requirements are ambiguous and multiple
          stakeholders
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

  <ExperienceSection id="experience">
      <h2>Work experience</h2>

    <ExperienceItem logo="/Monzo-Emblem.png"
                    title="Technical Lead / Senior Software Engineer II at Monzo Bank"
                    dates="Mar 2021 - present">
      <div class="paragraph">Tech Lead of Financial Crime Decisioning squad, looking for signs of money laundering / terrorist
      financing amongst 9M+ Monzo's customers.</div>

      <div class="paragraph">
        Notable achievements:
        <ul>
      <li>launched a new Customer Risk Assessment system, allowing Monzo to assess risky customers more
      accurately. This resulted in a decrease in signup rejection rates and better identification of bad actors.</li>
      <li>launched a new Sanction Screening system, allowing the bank to start accepting incoming
      international payments</li>
      <li>expanded and matured Transaction Monitoring system, to prevent and detect even more types of
      crime in real-time and to achieve compliance with regulations</li>
       </ul>
      </div>

      <div class="paragraph">
      Recent highlights:
        <ul>
      <li>prevented >£100K in money laundering losses, by introducing a control that automatically flags
      complex cases for Senior Financial Crime Investigators</li>
      <li>reduced the operational cost of running the Transaction Monitoring system by >£175K/year, through
      optimizations to the backend code</li>
        </ul>
      </div>

      I've been Senior Software Engineer II at Monzo from the start but also took on the Tech Lead hat in
      October 2021.
    </ExperienceItem>

    <ExperienceItem logo="/ocado.png"
                    title="Principal Software Engineer at Ocado Technology"
                    dates="Mar 2014 - Feb 2021">
      <div class="paragraph">
      I was a member of the Data Platform and Machine Learning Services teams. Together we:
        <ul>
      <li>cut the storage and processing cost at least 5 times, by migrating analytical data and associated
      workflows from Oracle to the GCP cloud</li>
      <li>improved quality and availability of data, by driving a cultural change in the organization to treat data
      as a first-class citizen</li>

      <li>decreased lead time for data / ML projects by at least the factor of 4, by applying improvements and
      automation to the entire process - starting from data exploration to deployment and monitoring</li>
        </ul>
      </div>

      I was Senior Software Engineer at the beginning, but then gradually moved to being Team Leader and
      then Principal Software Engineer.
    </ExperienceItem>

    <ExperienceItem logo="/hadapt.png"
                    title="Software Engineer at Hadapt"
                    dates="Sep 2011 - Dec 2013">
      I worked on the proprietary distributed storage system (similar to HDFS).
    </ExperienceItem>
  </ExperienceSection>

  <ExperienceSection id="education">
    <h2>Education</h2>
    <ExperienceItem logo="/uwr.png"
                    title="Bachelor's degree in Computer Science at University of Wrocław"
                    dates="2009 - 2012"/>
    </ExperienceSection>

  <Footer>© 2024 Przemek Pastuszka. All Rights Reserved.</Footer>
</template>

<style scoped>
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

.paragraph {
  font-size: 0.9rem;
  margin-bottom: 20px;
  line-height: 1.8;
  text-align: justify;
  text-justify: inter-word;
}

.paragraph li {
  margin-left: 30px
}

.hero .image {
  flex: 1;
  text-align: center;
}

.hero .image img {
  max-width: 100%;
  height: auto;
}

/* Media Queries for Mobile Responsiveness */
@media (max-width: 768px) {
  .hero {
    flex-direction: column;
  }

  .hero .content {
    padding-right: 0;
  }
}
</style>
