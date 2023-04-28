<template>
  <div class="bg-gray-800 py-24 sm:py-32">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
          <div>
            <h2 class="text-base font-semibold leading-7 text-indigo-600">Minha jornada</h2>
            <p class="mt-2 text-3xl font-bold tracking-tight text-white sm:text-4xl">Experiencias Profissionais</p>
          </div>
      <div class="mx-auto mt-5 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 dark:border-gray-700 pt-10 sm:mt-10 sm:pt-16 lg:mx-0 lg:max-w-none lg:grid-cols-3" >
        <article
          v-for="experience in professional_experiences"
          :key="experience.id"
          class="flex max-w-xl flex-col items-start justify-between bg-gray-900 p-6 rounded-2xl border border-gray-600 cursor-pointer w-full"
        >
          <div class="flex items-center gap-x-4 text-xs w-full">

            <div v-if="experience.departure_date == 'current'" class="flex gap-3 items-center w-full justify-between">
              
              <p class="text-xs text-gray-500">{{ experience.admission_date }} - {{ experience.departure_date }}</p>

              <span class="flex items-center gap-x-1.5 rounded-md px-3 py-1 text-xs font-medium text-white ring-1 ring-inset ring-gray-700">
                <svg class="h-1.5 w-1.5 fill-green-400" viewBox="0 0 6 6" aria-hidden="true">
                  <circle cx="3" cy="3" r="3" />
                </svg>
                online
              </span>

            </div>

            <div v-if="experience.departure_date !== 'current'" class="flex gap-3 items-center w-full justify-between">
              
              <p class="text-xs text-gray-500">{{ experience.admission_date }} - {{ experience.departure_date }}</p>

              <span class="flex items-center gap-x-1.5 rounded-md px-3 py-1 text-xs font-medium text-white ring-1 ring-inset ring-gray-700">
                <svg class="h-1.5 w-1.5 fill-red-800" viewBox="0 0 6 6" aria-hidden="true">
                  <circle cx="3" cy="3" r="3" />
                </svg>
                offline
              </span>

            </div>

          </div>
          <div class="relative mt-4 flex items-center gap-x-4">
            <img
              :src="experience.imageUrl"
              alt=""
              class="h-10 w-10 rounded-full bg-gray-50"
            />
            <div class="text-sm leading-6">
              <p class="font-semibold text-white">
                <a :href="experience.company_website">
                  <span class="absolute inset-0" />
                  {{ experience.company_name }}
                </a>
              </p>
              <p class="text-gray-400">{{ experience.role }}</p>
            </div>
          </div>

        </article>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        professional_experiences: [
          {
            id: 1,
            company_name: "UDS Soluçôes",
            company_website: "https://uds.com.br",
            imageUrl: "https://media.licdn.com/dms/image/C4E0BAQGA6GugamGwdg/company-logo_200_200/0/1584452706815?e=1691020800&v=beta&t=QqC6GN5ap1IqAVzMSgHrR9FxtcVTxR8lAtpxF6DMEH8",
            role: "Desenvolvedor Full-Stack Pleno",
            admission_date: "2022-03-16",
            departure_date: "current",
            activities: [
              "Stacks: WordPress e Vue.js",
              "Metodologia ágil: SCRUM",
              "Desenvolvimento em (WP / PHP / Laravel / Vue.js)",
              "Desenvolvimento de layouts (Figma)",
              "Jira / Bitbucket",
              "Correção de bugs",
            ],
          },
          {
            id: 2,
            company_name: "Google",
            company_website: "https://google.com",
            imageUrl: "https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png",
            role: "Software Engineer",
            admission_date: "2020-01-01",
            departure_date: "2022-01-01",
            activities: [
              "Stacks: WordPress e Vue.js",
              "Metodologia ágil: SCRUM",
              "Desenvolvimento em (WP / PHP / Laravel / Vue.js)",
              "Desenvolvimento de layouts (Figma)",
              "Jira / Bitbucket",
              "Correção de bugs",
            ],
          },
          {
            id: 3,
            company_name: "Microsoft",
            company_website: "https://microsoft.com",
            imageUrl: "https://www.microsoft.com/en-us/research/wp-content/themes/microsoft-research/images/Microsoft-logo_rgb_cropped.png",
            role: "Software Developer",
            admission_date: "2018-01-01",
            departure_date: "2020-01-01",
            activities: [
              "Stacks: WordPress e Vue.js",
              "Metodologia ágil: SCRUM",
              "Desenvolvimento em (WP / PHP / Laravel / Vue.js)",
              "Desenvolvimento de layouts (Figma)",
              "Jira / Bitbucket",
              "Correção de bugs",
            ],
          },
          {
            id: 4,
            company_name: "Amazon",
            company_website: "https://amazon.com",
            imageUrl: "https://d1.awsstatic.com/logos/aws-logo-lockups/poweredbyaws/PB_AWS_logo_RGB_stacked_REV_SQ.91cd4af1a2e3d7a31f6dc9b7d6488d975bbdd7a6.png",
            role: "Software Engineer",
            admission_date: "2016-01-01",
            departure_date: "2018-01-01",
            activities: [
              "Stacks: WordPress e Vue.js",
              "Metodologia ágil: SCRUM",
              "Desenvolvimento em (WP / PHP / Laravel / Vue.js)",
              "Desenvolvimento de layouts (Figma)",
              "Jira / Bitbucket",
              "Correção de bugs",
            ],
          },
        ],
      }
    },
    methods: {
      lastSeenDate(departure_date) {
        const today = new Date();
        const lastSeen = new Date(departure_date);
        const timeDiff = Math.abs(today.getTime() - lastSeen.getTime());
        const daysDiff = Math.ceil(timeDiff / (1000 * 3600 * 24));
        return `Experiência encerrada a ${daysDiff} dias...`;
      }
    }
  }
</script>
