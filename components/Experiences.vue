<template>
  <div class="bg-gradient-to-t from-gray-950 to-gray-900 py-24" id="experiencias">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
          <div>
            <h2 class="text-base font-semibold leading-7 text-indigo-600">Minha jornada</h2>
            <p class="mt-2 text-3xl font-bold tracking-tight text-white sm:text-4xl">Experiencias Profissionais</p>
          </div>
      <div class="mx-auto mt-4 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-10 dark:border-gray-700 pt-10 lg:mx-0 lg:max-w-none lg:grid-cols-3" >
        <article
          v-for="experience in professional_experiences"
          :key="experience.id"
          class="flex max-w-xl flex-col items-start justify-between bg-gray-900 p-6 rounded-2xl border border-gray-600 cursor-pointer w-full"
        >
          <div class="flex items-center gap-x-4 text-xs w-full">

            <div v-if="experience.departure_date == 'Atual'" class="flex gap-3 items-center w-full justify-between">
              
              <p class="text-xs text-gray-500">{{ formatDate(experience.admission_date) }} - {{ experience.departure_date }}</p>

              <span class="flex items-center gap-x-1.5 rounded-md px-3 py-1 text-xs font-medium text-white ring-1 ring-inset ring-gray-700">
                <svg class="h-1.5 w-1.5 fill-green-400" viewBox="0 0 6 6" aria-hidden="true">
                  <circle cx="3" cy="3" r="3" />
                </svg>
                online
              </span>

            </div>

            <div v-if="experience.departure_date !== 'Atual'" class="flex gap-3 items-center w-full justify-between">
              
              <p class="text-xs text-gray-500">{{ formatDate(experience.admission_date) }} - {{ formatDate(experience.departure_date) }}</p>

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
            departure_date: "Atual",
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
            company_name: "Trinity Web",
            company_website: "https://thetrinityweb.com.br/",
            imageUrl: "https://media.licdn.com/dms/image/C4D0BAQEr88R9sjHijw/company-logo_200_200/0/1643842154329?e=1691020800&v=beta&t=dybsG7_Qzc2z1g2iK3HSxP0GNDz7tV9UPh9Ne1OO-EQ",
            role: "Proprietário / Desenvolvedor Full-Stack",
            admission_date: "2019-01-11",
            departure_date: "Atual",
            activities: [
              "Fundei a Trinity Web, para poder aplicar todo o conhecimento que adquiri com o tempo, e ao mesmo tempo é o nome que eu assino todos meus freelances. ",
            ],
          },
          {
            id: 3,
            company_name: "8D Propaganda",
            company_website: "https://8dpro.com/",
            imageUrl: "https://scontent.fcgh3-1.fna.fbcdn.net/v/t39.30808-6/278249824_5012447438842123_5641726537805973070_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=09cbfe&_nc_ohc=NBpB8ntRRo0AX9op4Va&_nc_ht=scontent.fcgh3-1.fna&oh=00_AfBOi5LMhjc1289cf6D6jo75kIeP2nvE2OuQVe4JGZXYUg&oe=644F7C06",
            role: "Desenvolvedor Front-End",
            admission_date: "2021-01-01",
            departure_date: "2022-05-01",
            activities: [
            ],
          },
          {
            id: 4,
            company_name: "Vollup Creative Agency",
            company_website: "https://vollup.com",
            imageUrl: "https://media.licdn.com/dms/image/C510BAQFXhaha2EFu6A/company-logo_200_200/0/1519873786047?e=1691020800&v=beta&t=kX8-gZ5pR1Szqxyj3qqi6Cx7MhSkYCAorTeXGd714q0",
            role: "Desenvolvedor Front-End",
            admission_date: "2019-07-01",
            departure_date: "2021-01-01",
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
            id: 5,
            company_name: "Adesse Marketing Digital",
            company_website: "https://vollup.com",
            imageUrl: "https://media.licdn.com/dms/image/C4E0BAQEBJ5OiLcxmLw/company-logo_200_200/0/1519861971238?e=1691020800&v=beta&t=G7kwq_24D6Hpg-Bn3Zmp9Nt2t1vJ4japi79dChxkfLI",
            role: "Estágiario / Web Designer",
            admission_date: "2017-07-01",
            departure_date: "2019-02-01",
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
      formatDate(inputDate) {
        const year = inputDate.slice(0, 4);
        const month = inputDate.slice(5, 7);
        return `${month}/${year}`;
      },
    }
  }
</script>
