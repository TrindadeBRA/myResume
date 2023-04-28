<template>
    <div class="bg-gray-800 py-24 sm:py-20">
      <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto grid max-w-2xl grid-cols-1 gap-x-8 gap-y-16 sm:gap-y-20 lg:mx-0 lg:max-w-none lg:grid-cols-3">
          <div>
            <h2 class="text-base font-semibold leading-7 text-indigo-600">Conhecimentos gerais</h2>
            <p class="mt-2 text-3xl font-bold tracking-tight text-white sm:text-4xl">Minhas Skills</p>
            <p class="mt-6 text-base leading-7 text-gray-300">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Maiores impedit perferendis suscipit eaque, iste dolor cupiditate blanditiis ratione.</p>
          </div>
          <dl class="col-span-2 grid grid-cols-1 gap-x-8 gap-y-3 text-base leading-7 text-gray-300 sm:grid-cols-3">
            <div v-for="(skill, index) in skills" :key="index" class="relative pl-9">
              <dt class="font-semibold text-white">
                <CheckIcon class="absolute left-0 top-1 h-5 w-5 text-indigo-500" aria-hidden="true" />
                {{ skill }}
              </dt>
            </div>
          </dl>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { CheckIcon } from '@heroicons/vue/20/solid'
  
  const features = [
    {
      name: 'Invite team members',
      description: 'Rerum repellat labore necessitatibus reprehenderit molestiae praesentium.',
    },
    { name: 'List view', description: 'Corporis asperiores ea nulla temporibus asperiores non tempore assumenda aut.' },
    {
      name: 'Keyboard shortcuts',
      description: 'In sit qui aliquid deleniti et. Ad nobis sunt omnis. Quo sapiente dicta laboriosam.',
    },
    {
      name: 'Calendars',
      description: 'Sed rerum sunt dignissimos ullam. Iusto iure occaecati voluptate eligendi fugiat sequi.',
    },
    { name: 'Notifications', description: 'Quos inventore harum enim nesciunt. Aut repellat rerum omnis adipisci.' },
    { name: 'Boards', description: 'Quae sit sunt excepturi fugit veniam voluptatem ipsum commodi.' },
    {
      name: 'Reporting',
      description: 'Eos laudantium repellat sed architecto earum unde incidunt. Illum sit dolores voluptatem.',
    },
    {
      name: 'Mobile app',
      description: 'Nulla est saepe accusamus nostrum est est. Fugit voluptatum omnis quidem voluptatem.',
    },
  ]

  const skills = [
    'WordPress',
    'Vue.js',
    'Laravel',
    'HTML',
    'CSS / SASS',
    'Bootstrap',
    'Tailwind',
    'jQuery',
    'JS',
    'REST API',
    'Axios',
    'PHP',
    'PHPUnit',
    'AJAX',
    'CRUD',
    'MySQL',
    'Metodologia ágil: SCRUM',
    'POO',
    'SOLID',
    'Git e Versionamento',
    'GitHub / Bitbucket',
    'cPanel',
    'PHPMyAdmin',
    'Desenv. de Temas (WP)',
    'Desenv. de Plugins (WP)',
    'SEO / Otimizações',
    'Jira / Trello / Runrun.it',
    'yarn / npm / composer',
    'PSD / XD / FIGMA',
    'Páginas responsivas'
  ]
  </script>