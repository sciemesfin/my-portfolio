<template>
  <div class="pt-20 md:pt-32 h-full">
    <div
      class="mx-auto md:max-w-7xl h-full w-[100%] px-2 py-10 sm:px-6 lg:px-8"
    >
    <h1 class="text-xl my-8 mb-10 text-center md:text-7xl font-extrabold py-2">Projects Delivered</h1>
      <section class="grid grid-cols-1 md:grid-cols-3 gap-4">
        <div class="max-w-lg mx-auto" v-for="(item, i) in items" :key="i">
          <div
            class="bg-white shadow-md border border-gray-200 rounded-lg max-w-sm mb-5"
          >
            <a href="#">
              <img
                class="rounded-t-lg max-h-[250px] w-full"
                :src="item.image"
                alt=""
              />
            </a>
            <div class="p-5">
              <a href="#">
                <h5
                  class="text-gray-900 font-bold text-2xl tracking-tight mb-2"
                >
                  {{ item.title }}
                </h5>
              </a>
              <p class="font-normal text-gray-700 mb-3 three-line">
                {{ item.description }}
              </p>
              <nuxt-link
                class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-3 py-2 text-center inline-flex items-center"
                :href="item.companyWebsite"
                target="_blank"
              >
                Read more
              </nuxt-link>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script setup>
import astra from "../assets/projects/astra.png";
import tesfacoffee from "../assets/projects/tesfacoffe.png";
import sharegebeya from "../assets/projects/sharegebeya.png";
import kpe from "../assets/projects/kpe.png";
import moneyave from  "../assets/projects/moneyave.png";
import lms  from  "../assets/projects/lms.jpeg";

const items = [
  {
    title: "Astra ERP Systems",
    companyWebsite: "https://poshakconsultancy.com",
    companyName: "Poshak Consultancy Plc",
    description: `Enterprise Resource Planning Software developed for Garment and Fashion industries. In this project we developed a system that will optimize cut order planing,
       operators' performance and machine efficiency monitoring, and quality assurance. The system also handles other
       servcies like Human resorces, accounting and finance, reports, and etc. `,
    image: astra,
  },
  {
    title: "Tesfa Coffee Website",
    companyWebsite: "https://www.tesfacoffee.com",
    companyName: "Tesfa Coffee Trade",
    description: `A web based system that will help Tesfa Coffee Trade to display their products to their intenational customers.
      Tesfa Coffee is a family-run coffee roasting company based in Addis Ababa, Ethiopia. After 6 years of working on 
      local Coffee business, we realized that our exeprience, customer feedback, our technical skills, and our Ethiopian 
      value can be put togather to create a unique and high quality Coffee Brand that will transform customer's feeling to 
      the hightest level`,
    image: tesfacoffee,
  },
  {
    title: "Learning Management System",
    companyWebsite: "https://www.tesfacoffee.com",
    companyName: "Tesfa Coffee Trade",
    description: `A learning management and school portal system that allow universities in Ethiopia to handle their teaching
    and learning process easier. This system is being used by 11 local universities.`,
    image: lms
  },
  {
    title: "Customer Onboarding App",
    companyWebsite: "https://bankpaytechnologies.com",
    companyName: "BankPay Technologies LTD",
    description: `Android and IOS app that will help Financial comnpanies to onboard their customers easily. The system allows
    customers's authentication using email and password, video/audio based auth, or face recognition technologies.`,
    image:
      "https://static.liveperson.com/static-assets/2022/02/11140627/Security_1-Photo-KS_02-11%402x.png",
  },
  {
    title: "Shemsu Souq",
    companyWebsite: "https://shemsusouq.com",
    companyName: "CodeBlue Computers",
    description: `A B2B and B2C eCommerce project developed from the customization of cs-cart tech stacks. The eCommerce is developed
    to capture the marketplace, shopping, and shipment business in Ethiopia.`,
    image: "https://cdn2.hubspot.net/hubfs/53/ecommerce%20marketing.jpg",
  },
  {
    title: "Money Transfer System",
    companyWebsite: "https://moneyave.com",
    companyName: "Money Avenue LLC",
    description: `Android and IOS app helps customers of Money Avenue LLC to transfer money money easily. Custoemrs can link their 
    Bank accounts to this system and manage their transactions amazingly.`,
    image:moneyave
  },
  {
    title: "Car Tracking System",
    companyWebsite: "https://t1factory.com",
    companyName: "Tech 1 Factory LLC",
    description: `Android and IOS app, and a web based dispatcher. We have developed apps for customers and clients separately.
    The tracking company uses the dispatching web based software to monitor the tracking process.`,
    image:
      "https://www.touchworldtech.com/images/gps-vehicle-tracking-dubai-uae-1.png",
  },
  {
    title: "Share Gebeya Marketplace",
    companyWebsite: "https://sharegebeya.com",
    companyName: "TechEthio IT Solution Plc",
    description: `Android app, and web app that allow people to sell and buy shares online in Ethiopia.`,
    image: sharegebeya,
  },
  {
    title: "ERP for Kenema Pharmacies",
    companyWebsite: "https://kenemape.com",
    companyName: "Kenema Pharmacies Enterprise",
    description: `Web based ERP system that helps Kenema Pharmacies Enterprise to automate and digital whole activities of the company. `,
    image:kpe
  },
];
</script>

<style>
.three-line {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2; /* number of lines to show */
  line-clamp: 2;
  -webkit-box-orient: vertical;
}
</style>
