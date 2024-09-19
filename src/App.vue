<template>
  <Navigation/>

  <section id="about" class="scroll-mt-20">
    <div class="container mx-auto flex flex-wrap max-w-6xl">
      <div class="w-full md:w-1/2 p-4 mb-8 md:mb-0 space-y-4">
        <p class="text-lg text-gray-600">
          I'm a <strong>product-oriented engineer</strong>, caring deeply about business metrics and leveraging data to
          inform the decision-making process.
        </p>
        <p class="text-lg text-gray-600">
          I'm <strong>seasoned in delivering complex projects</strong>, where requirements are ambiguous and multiple
          stakeholders often pursue different objectives.
        </p>
        <p class="text-lg text-gray-600">
          I always try to be very intentional and pragmatic about delivering for the short vs. long term, shifting gears
          between strategic and tactical thinking as needed.
        </p>
      </div>
      <div class="w-full md:w-1/2 p-4 flex justify-center">
        <img src="https://via.placeholder.com/500x300" alt="Placeholder Image" class="w-full h-auto">
      </div>
    </div>
  </section>

  <div id="experience" class="container mx-auto p-4 scroll-mt-20 max-w-6xl">
    <h2 class="text-3xl font-semibold text-gray-800 mb-6">Work experience</h2>

    <ExperienceItem logo="/Monzo-Emblem.png"
                    title="Technical Lead / Senior Software Engineer II at Monzo Bank"
                    dates="Mar 2021 - present">
      <div class="space-y-4">
        <div>
          Tech Lead of Financial Crime Decisioning squad, looking for signs of money laundering/terrorist financing amongst 9M+ Monzo customers.
        </div>

        <div>
          Notable achievements:
          <ul class="list-disc ml-6">
            <li>Launched a new Customer Risk Assessment system, allowing Monzo to assess risky customers more accurately, resulting in decreased signup rejection rates and better identification of bad actors.</li>
            <li>Launched a new Sanction Screening system, allowing the bank to start accepting incoming international payments.</li>
            <li>Expanded and matured Transaction Monitoring system to prevent and detect more types of crime in real-time and achieve compliance with regulations.</li>
          </ul>
        </div>

        <div>
          Recent highlights:
          <ul class="list-disc ml-6">
            <li>Prevented >£100K in money laundering losses by introducing a control that flags complex cases for Senior Financial Crime Investigators.</li>
            <li>Reduced the operational cost of running the Transaction Monitoring system by >£175K/year through backend code optimizations.</li>
          </ul>
        </div>

        <p>I've been Senior Software Engineer II at Monzo from the start but also took on the Tech Lead role in October 2021.</p>
      </div>
    </ExperienceItem>

    <ExperienceItem logo="/ocado.png"
                    title="Principal Software Engineer at Ocado Technology"
                    dates="Mar 2014 - Feb 2021">
      <div class="text-sm text-gray-700 mb-4">
        I was a member of the Data Platform and Machine Learning Services teams. Together we:
        <ul class="list-disc ml-6">
          <li>Cut storage and processing costs by at least 5 times by migrating analytical data and workflows from Oracle to the GCP cloud.</li>
          <li>Improved the quality and availability of data by driving a cultural change to treat data as a first-class citizen.</li>
          <li>Decreased lead time for data/ML projects by at least 4 times by automating the entire process—from data exploration to deployment and monitoring.</li>
        </ul>
      </div>
    </ExperienceItem>

    <ExperienceItem logo="/hadapt.png"
                    title="Software Engineer at Hadapt"
                    dates="Sep 2011 - Dec 2013">
      <p class="text-sm text-gray-700">I worked on the proprietary distributed storage system (similar to HDFS).</p>
    </ExperienceItem>
  </div>

  <div id="education" class="container mx-auto p-4 scroll-mt-20 max-w-6xl">
    <h2 class="text-3xl font-semibold text-gray-800 mb-6">Education</h2>
    <ExperienceItem logo="/uwr.png"
                    title="Bachelor's degree in Computer Science at University of Wrocław"
                    dates="2009 - 2012"/>
  </div>

  <footer class="bg-gray-900 text-white py-6 text-center">
    © 2024 Przemek Pastuszka. All Rights Reserved.
  </footer>
</template>

<script lang="ts">
import Navigation from "@/components/Navigation.vue";
import ExperienceItem from "@/components/ExperienceItem.vue";

export default {
  components: {
    ExperienceItem,
    Navigation,
  },
}
</script>