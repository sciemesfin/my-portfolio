<template>
  <div class="pt-20 md:pt-32 h-full">
    <div
      class="mx-auto md:max-w-7xl h-full w-[100%] px-2 py-10 sm:px-6 lg:px-8"
    >
      <div class="grid grid-cols-3 gap-4">
        <div v-for="(item, i) in items" :key="i">
          <div class="shadow rounded-md cursor-pointer hover:bg-gray-200">
            <div class="p-5">
              <img
                :src="item.image"
                alt=""
                class="object-contain mx-auto max-h-[150px] w-[150px] rounded-full"
              />
            </div>
            <div class="p-5">
              <p class="text-xl text-center pb-3 md:text-4xl font-extrabold">
                {{ item.title }}
              </p>
              <p class="text-center text-sm">{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import astra from "../assets/astra.png";
const items = [
  {
    title: "Poshak ERP",
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
    image: "https://www.tesfacoffee.com/img/logo.7cd9d40b.jpg",
  },
  {
    title: "Learning Management System",
    companyWebsite: "https://www.tesfacoffee.com",
    companyName: "Tesfa Coffee Trade",
    description: `A learning management and school portal system that allow universities in Ethiopia to handle their teaching
    and learning process easier. This system is being used by 11 local universities.`,
    image:
      "https://community.nasscom.in/sites/default/files/styles/960_x_600/public/media/images/Benefits-of-Using-an-LMS%20%281%29.png?itok=cS4lXOh2",
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
    image:
      "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRAlwCsmThtt6NA7wS3HBnNkBlsTNjSBDA0Og&usqp=CAU",
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
];
</script>
