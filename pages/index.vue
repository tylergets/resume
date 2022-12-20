<template>
  <div class="bg-gray-200 min-h-screen">
    <div class="p-6 mx-auto max-w-7xl bg-white min-h-screen shadow">
      <div id="header" class="flex flex-col gap-4">
        <div class="text-4xl">Tyler Getsay</div>
        <div class="text-xl">Full Stack Developer, Architect, and Product Manager</div>
        <div class="leading-7">
          {{intro}}
        </div>
        <div class="flex gap-4">
          <div class="flex items-center gap-2">
            <Icon name="uil:github" class="text-2xl" />
            <a class="link" href="https://github.com/tylergets">TylerGets</a>
          </div>
          <div class="flex items-center gap-2">
            <Icon name="uil:linkedin" class="text-2xl" />
            <a class="link" href="https://linkedin.com/in/tylergetsay">TylerGetsay</a>
          </div>
          <div class="flex items-center gap-2">
            <Icon name="uil:phone-alt" class="text-2xl" />
            <a class="link" href="tel:+14404094081">+1 (440) 409-4081</a>
          </div>
          <div class="flex items-center gap-2">
            <Icon name="uil:fast-mail" class="text-2xl" />
            <a class="link" href="mailto:tylergetsay@gmail.com">TylerGetsay@gmail.com</a>
          </div>
        </div>
      </div>
      <div>
        <div v-for="section in sections" class="flex flex-col gap-2 mt-6">
          <div class="text-2xl font-bold">{{section.title}}</div>
          <div v-if="section.subtitle" class="text-lg">{{section.subtitle}}</div>
          <div v-if="section.body">{{section.body}}</div>
          <div v-if="section.list" class="flex flex-wrap gap-2 mt-2">
            <div v-for="item in section.list" class="bg-gray-100 px-2 py-1">
              {{item}}
            </div>
          </div>
          <div v-if="section.experiences" class="flex flex-col gap-4 mt-2">
            <div v-for="exp in section.experiences" class="flex flex-col gap-2">
              <div class="text-xl font-medium">{{exp.title}}</div>
              <div v-if="exp.position" class="">{{exp.position}}</div>
              <div class="text-sm text-gray-600">{{exp.time}}</div>
              <div>{{exp.description}}</div>
              <div v-if="exp.list" class="flex flex-col gap-2 ">
                <li v-for="item in exp.list"  class="list-inside list-disc">
                  {{item}}
                </li>
              </div>
            </div>
          </div>
          <div v-if="section.education" class="flex flex-col gap-4 mt-2">
            <div v-for="edu in section.education" class="flex flex-col gap-2">
              <li class="list-inside list-disc">
                {{edu}}
              </li>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const intro = "As a full stack programmer with management experience, I have a unique blend of technical expertise and leadership skills. I have successfully led cross-functional teams to deliver high-quality products on time, and I am skilled at managing multiple projects simultaneously. In addition to my technical skills, I have strong communication and problem-solving abilities, which have consistently helped me to identify and address challenges and drive the success of projects. I believe that my technical skills and managerial experience make me a valuable asset to any organization.";

const sections = [
  {
    title: 'Skills',
    subtitle: 'I have hands-on experience taking products from the white-board to production using the following technologies:',
    list: ['PHP','NodeJS','Vue','React','Angular','GraphQL','Android','Python','Dart','Flutter','Bluetooth Low Energy','LoRaWAN','AWS','Kubernetes']
  },
  {
    title: 'Work Experience',
    experiences: [
      {
        title: 'Visitu',
        position: 'Lead Architect & Full Stack Developer',
        time: '2018 - Present',
        description: 'I joined Visitu in September of 2018 to help accelerate product development and build a team of developers who are passionate about campus safety. Since arriving I have led the development team through building the next generation of our core products, the launch of these products, and the continued support of them.',
        list: [
            'Architected a complete solution to screen and track every visitor, staff, or student entering a corporate or school lobby.',
            'Extended the system to screen and contact trace millions of people for COVID-19 symptoms at hundreds of K12 schools.',
            'Built the frontend web dashboard used by school administrators & receptionists to monitor/perform all system functions.',
            'Managed a team of 4 developers and contractors who build frontend clients for Vuejs, iOS, Flutter, and embedded Linux.',
            'Created development workflows including ticket capture, PR reviews, CI tests, automatic releases, and branch protections.',
            'Helped sales close multi-location deals with Fortune 500 companies by careful requirements gathering.',
            'Deployed a cross-platform mobile app to thousands of end-users',
            'Acted as lead designer for all customer-facing interfaces.'
        ]
      },
      {
        title: 'MedaCheck',
        position: 'Software Developer',
        description: 'Throughout my years at MedaCheck I built many solutions surrounding medication adherence, Bluetooth health monitors, real-time dashboards, and mobility management solutions. Additional knowledge gained involved HIPAA compliance, SOC2 compliance, and UX design. Our solutions were used by area hospitals in IRB approved studies.',
        time: '2016 - 2018',
        list: [
            'Architected and built a frontend dashboard for the companies legacy API.',
            'Dashboard was used by researchers to create studies and examine results.',
            'Built an Android application for interfacing with a BLE spirometer, used in academic study (PMID 34153516)',
            'Setup automated CI and CD across all code bases to improve developer efficiency.',
            'Built an end-to-end data system to securely transfer wearable health data to a clinicians EMR system.',
            'Developed a custom version of Android OS deployed to custom medical hardware.',
            'Consulted on database requirements to maintain HIPAA compliance.',
        ]
      },
      {
        title: 'Fanvester',
        time: '2015 - 2016',
        position:'Founder and CTO',
        description: 'Founded by a few friends, we took on the live entertainment industry by attempting to build a crowd funding website for live concerts at underserved areas through the USA',
        list: [
            'Built a backend portal for everyone involved in a live show; including venue and tour operators',
            'Created a payment system which processed payments and refunds for 250k worth of pre-sold tickets.',
            'Participated in UpTech 4 accelerator program.',
        ]
      },
      {
        title: 'Freelancer',
        time: '2005 - 2016',
        description: 'I have helped many small to medium size businesses navigate the growing web landscape; this has manifested in many websites, apps, and internal tools which have been used by millions of users; and subsequently produced millions of dollars in revenue.',
        list: [
            'Generated an additional two million dollars in revenue for a local chicken hatchery with a new ecommerce platform.',
            'Generated thousands of leads for a local shredding company through new website and SEO.',
        ]
      }
    ]
  },
  {
    title: 'Education',
    subtitle: 'University of Cincinnati',
    body: 'I received a bachelors degree in Information Technology from the University of Cincinnati in 2019.',
    education: [
        'Utilized Credit by Exam for a large percentage of course load.',
        'Enrolled in Linder College of Business classes as non-matriculated student.'
    ]
  }
]
</script>

<style scoped>

</style>