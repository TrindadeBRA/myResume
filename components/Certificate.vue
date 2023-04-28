<template @keydown="handleKeyDown">
    <div class="bg-gray-900 py-24 sm:py-20" id="certificados">
      <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-2xl text-center">
          <h2 class="text-base font-semibold leading-7 text-indigo-600">Estudos</h2>
          <h2 class="text-3xl font-bold tracking-tight text-white sm:text-4xl">Certificados</h2>
          <p class="mt-2 text-lg leading-8 text-gray-300">Learn how to grow your business with our expert advice.</p>
        </div>
        <div class="mx-auto mt-16 grid max-w-2xl grid-cols-1 sm:grid-cols-2 gap-x-8 gap-y-10 lg:mx-0 lg:max-w-none lg:grid-cols-4">

          <article v-for="post in posts" :key="post.id" class="flex flex-col items-start justify-between cursor-pointer bg-gray-800 py-5 px-5 rounded-3xl shadow-md shadow-gray-600"
          @click="openModal(post.imageUrl)">
            <div class="relative w-full cursor-pointer mb-5">
              <img :src="post.imageUrl" alt="" class="aspect-[16/9] w-full rounded-2xl bg-gray-100 object-cover sm:aspect-[2/1] lg:aspect-[3/2] cursor-pointer"/>
              <div class="absolute inset-0 rounded-2xl ring-1 ring-inset ring-white/10" />
            </div>
            <div class="w-full">
              <div class="group relative">
                <h3 class="mt-2 text-base font-semibold leading-6 text-white group-hover:text-gray-300 text-center cursor-pointer line-clamp-2" @click="openModal(post.imageUrl)">
                  {{ post.title }}
                </h3>
                <p class="mt-2 text-base font-light italic leading-6 text-white group-hover:text-gray-300 text-center cursor-pointer" @click="openModal(post.imageUrl)">
                  {{ post.institution }}
                </p>
              </div>
              <div class="mt-2 flex items-center gap-x-4 text-xs justify-around pb-2">
                <time :datetime="post.datetime" class="text-gray-300">{{ post.date }}</time>
              </div>
            </div>
          </article>

          <!-- Modal -->
          <div v-show="showModal" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-75 z-50">
            <div class="w-4/5 lg:w-3/5 2xl:w-2/6 relative">
              <img :src="showImageUrl" alt="Imagem" class="max-w-full">
              <button @click="closeModal" class="absolute -top-8 -right-8 m-4 p-2 rounded-full bg-white text-gray-800 shadow-md">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                </svg>
              </button>
            </div>
          </div>
          
        </div>
      </div>
    </div>
  </template>

  <script>
  export default {
    data() {
      return {
        showModal: false,
        showImageUrl: "",
        posts: [
          {
            id: 1,
            title: 'Análise e Desenvolvimento de Sistemas',
            institution: 'UNIP – Universidade Paulista',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/analise-desenvolvimento-de-sistemas.webp',
            date: 'Jun 01, 2019',
            category: 'Graduação',
          },
          {
            id: 2,
            title: 'SOLID - Os 5 Princípios Para as Boas Práticas da POO',
            institution: 'Udemy – Jorge Sant Ana',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/solid-os-5-principios-para-as-boas-praticas-da-poo.webp',
            date: 'Abr 25, 2023',
            category: 'Horas',
          },
          {
            id: 3,
            title: 'Vue JS 3: Desenvolvimento Web Moderno com Vuex & Vue Router',
            institution: 'Udemy – Ivan Lourenço Gomes',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/vue-js-3.webp',
            date: 'Abr 14, 2023',
            category: 'Horas',
          },
          {
            id: 4,
            title: 'CSS Avançado - Sass, CSS Grid Layout e CSS Modules',
            institution: 'Udemy – Brunão Sousa',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/vue-js-3.webp',
            date: 'Abr 14, 2023',
            category: 'Horas',
          },
          {
            id: 5,
            title: 'Scrum para Desenvolvedores de Software',
            institution: 'Udemy – Bruno Coutinho',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/scrum-para-desenvolvedores-de-software.webp',
            date: 'Jan 05, 2023',
            category: 'Horas',
          },
          {
            id: 6,
            title: 'Git e Github Essencial para o Desenvolvedor',
            institution: 'Udemy – Geek University',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/git-e-github-essencial.webp',
            date: 'Jan 02, 2023',
            category: 'Horas',
          },
          {
            id: 7,
            title: 'Trilha Especializar',
            institution: 'Rocketseat',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/discover-especializar-certificate.webp',
            date: 'Out 14, 2022',
            category: 'Horas',
          },
          {
            id: 8,
            title: 'Trilha Fundamentar',
            institution: 'Rocketseat',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/discover-fundamentar-certificate.webp',
            date: 'Set 14, 2022',
            category: 'Horas',
          },
          {
            id: 9,
            title: 'Trilha Conectar',
            institution: 'Rocketseat',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/discover-conectar-certificate.webp',
            date: 'Ago 09, 2022',
            category: 'Horas',
          },
          {
            id: 10,
            title: 'PHP 7 Completo',
            institution: 'Hode',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/php7-hcode.webp',
            date: 'Jun 09, 2022',
            category: 'Horas',
          },
          {
            id: 11,
            title: 'PHP 7 Completo',
            institution: 'Udemy - Matheus Battisti',
            imageUrl: 'https://thetrinityweb.com.br/resume/images/certificados/git-github-avancado.webp',
            date: 'Mai 24, 2022',
            category: 'Horas',
          },
        ],
      };
    },
    methods: {
      openModal(imageUrl) {
        this.showImageUrl = imageUrl
        this.showModal = true;
        document.body.classList.add('overflow-hidden');
      },
      closeModal() {
        this.showModal = false;
        document.body.classList.remove('overflow-hidden');
      },
    },
  };
  </script>

