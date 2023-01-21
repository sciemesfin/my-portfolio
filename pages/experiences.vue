<template>
  <div class="pt-20 md:pt-32 h-full">
    <div
      class="mx-auto md:max-w-7xl h-full w-[100%] px-2 py-10 sm:px-6 lg:px-8"
    >
      <div class="md:flex h-full">
        <section class="hidden md:block w-full md:w-1/2 md:p-10">
          <h1 class="text-xl md:text-4xl font-bold py-2">Bio</h1>
          <p class="text-gray-500">
            Professional Software Engineer with 5 years of commercial experience
            as a Full stack developer, Frontend Developer, backend Developer,
            Mobile app developer, in Problem Solving, and APIs developer and
            integrations. I have worked on the development of problem solving
            projects for the Education sectors, Financial industries,
            E-Commerce, Transportation sectors, and Garment and Fashion
            industries. I love Programming; studying real world problems and
            looking for a better solution.
          </p>
          <div class="py-5">
            <h1 class="font-bold py-2 text-xl">Companies I have worked for</h1>
            <div v-for="(item, i) in experiences" :key="i" class="pl-3 pb-3">
              <nuxt-link
                :href="item.href"
                target="_blank"
                class="text-gray-600 flex items-center"
              >
                <span class="pr-5"> {{ i + 1 }}. {{ item.company }}</span>
                <div class="text-blue-600">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke-width="1.5"
                    stroke="currentColor"
                    class="w-4 h-4"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      d="M13.5 6H5.25A2.25 2.25 0 003 8.25v10.5A2.25 2.25 0 005.25 21h10.5A2.25 2.25 0 0018 18.75V10.5m-10.5 6L21 3m0 0h-5.25M21 3v5.25"
                    />
                  </svg>
                </div>
              </nuxt-link>
            </div>
          </div>
        </section>
        <section class="w-full h-full md:border-l p-2 md:px-10">
          <h1 class="text-xl md:text-4xl font-bold py-2">Experience</h1>
          <div v-for="(item, i) in experiences" :key="i">
            <div
              class="p-5 my-5 shadow-md border border-gray-300 rounded h-full"
            >
              <h1 class="text-gray-900 font-bold">
                {{ item.title }}
              </h1>
              <div class="flex justify-between items-center py-1">
                <div>
                  <p>
                    <nuxt-link
                      :href="item.href"
                      target="_blank"
                      class="font-bold text-sm text-blue-600 py-1"
                      >{{ item.company }}
                    </nuxt-link>
                  </p>
                  <p class="text-xs">
                    {{ item.location }}
                  </p>
                </div>
                <p v-if="item.endDate !== 'active'" class="text-sm">
                  {{ item.startDate }} - {{ item.endDate }}
                </p>
                <p v-else class="text-xs">
                  {{ item.startDate }} -
                  <span class="text-blue-600">{{
                    "Currently working here"
                  }}</span>
                </p>
              </div>
              <div class="pt-3">
                <p class="font-bold text-sm">Description</p>
                <div
                  v-for="(x, i) in item.description"
                  :key="i"
                  class="flex py-1 ml-3"
                >
                  <div class="text-blue-600 pt-2">
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke-width="3.5"
                      stroke="currentColor"
                      class="w-4 h-4"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M15 15l6-6m0 0l-6-6m6 6H9a6 6 0 000 12h3"
                      />
                    </svg>
                  </div>

                  <span class="pl-2 text-gray-500 text-sm">{{ x }}</span>
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
const experiences = [
  {
    href: "http://techethio.com",
    location: "Addis Ababa, Ethiopia (Hybrid)",
    title: "Lead Full Stack Developer",
    company: "TechEthio IT Solution Plc",
    startDate: "December, 2022",
    endDate: "active",
    description: [
      `Working as a Lead Full stack developer on ERP Projects using tech stacks:Flutter, Reactjs, Nextjs, GraphQL, TypeScript, Nodejs, MongoDB, AWS, Firebase, and Git`,
    ],
  },
  {
    href: "https://resultier.com",
    location: "Twin Falls, Idaho, USA (Remote)",
    title: "React Engineer",
    company: "Resultier Inc",
    startDate: "March, 2022",
    endDate: "September, 2022",
    description: [
      `Developed a Test Driven Learning Experience system using Next js, React js, GraphQL, TypeScript, PostgreSQL, Git, Jest, CI/CD, and AWS.`,
    ],
  },
  {
    href: "http://tech1factory.com",
    location: "Atlanta, Georgia, USA (Remote)",
    title: "Senior Software Developer",
    company: "Tech 1 Factory LLC",
    startDate: "November, 2020",
    endDate: "March, 2022",
    description: [
      "Developed web based applications using React, AWS Serverless, DynamoDB, and Angular.",
      "Developed a single standalone CRM system by integrating Salesforce, Facebook Ads, Google Ads, Google My Business, and Google Analytics",
      "Developed two applications using React Native for Car washing companies",
      "Developed a diversified marketplace IOS and Android apps using React Native and Firebase",
    ],
  },

  {
    href: "https://yesuitsolution.com",
    location: "Addis Ababa, Ethiopia (Onsite)",
    title: "Full Stack Developer",
    company: "Yesu IT Solution PLC",
    startDate: "September 2020",
    endDate: "November 2020",
    description: [
      `Developed a web based Learning Management system using Vue js, Loopback, MongoDB, and Moodle Content Management System`,
    ],
  },

  {
    href: "https://globedocket.com",
    location: "Addis Ababa, Ethiopia (Onsite)",
    title: "Full Stack Developer",
    company: "CodeBlue Computers PLC",
    startDate: "August 2020 ",
    endDate: "December 2020",
    description: [
      `Worked on customization of CS-CART eCommerce Content Management System and Developed B2C eCommerce web application`,
      `Developed eCommerce mobile app using React Native`,
    ],
  },

  {
    href: "https://poshakconsultancy.com",
    location: "Bahir Dar, Ethiopia (Onsite)",
    title: "Software Engineer",
    company: "Poshak Consultancy PLC",
    startDate: "December 2019",
    endDate: "September 2020",
    description: [
      `Worked as a scrum master`,
      `Developed Operators’ Performance Monitoring Software for Garment and Textile industries using Vue js, Vuetify, Loopback and MongoDB`,
      `Developed Daily Operations Management and Quality Monitoring Mobile Application for Garment and Textile industries using Flutter, Dart, Firebase, Loopback and MongoDB`,
    ],
  },

  {
    href: "https://bankpaytechnologies.com",
    location: "London, United Kingdom (Remote)",
    title: "Software Engineer",
    company: "BankPay Technologies LTD",
    startDate: "April, 2019",
    endDate: "October, 2019",
    description: [
      `Developed websites using Vuejs, Vuetify, Nodejs, and MySQL`,
      `Gave organized training for junior software engineers joining BankPay technologies LTD on Flutter and Dart, Vuejs, Scrum, Git, and GSuit`,
      `Developed a customer onboarding mobile app for Banks using Flutter and Firebase`,
    ],
  },

  {
    href: "https://ahadootec.com",
    location: "Addis Ababa, Ethiopia (Onsite)",
    title: "Software Developer",
    company: "AhadooTec ICT Solution PLC",
    startDate: "April, 2019",
    endDate: "October, 2019",
    description: [
      `Developed a Building Management System for Addis Ababa City Administration using Vuejs, Vuetify, Loopback, and MongoDB`,
      `Developed efficient auto-complete field plugins to be used everywhere it is required by AhadooTec Vue developers`,
    ],
  },
];
</script>
