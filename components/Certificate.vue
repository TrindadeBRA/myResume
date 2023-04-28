<template @keydown="handleKeyDown">
    <div class="bg-gray-900 py-24 sm:py-20" id="certificados">
      <div class="mx-auto max-w-7xl px-6 lg:px-8">
        <div class="mx-auto max-w-2xl text-center">
          <h2 class="text-base font-semibold leading-7 text-indigo-600">Estudos</h2>
          <h2 class="text-3xl font-bold tracking-tight text-white sm:text-4xl">Certificados</h2>
          <p class="mt-2 text-lg leading-8 text-gray-300">Learn how to grow your business with our expert advice.</p>
        </div>
        <div class="mx-auto mt-16 grid max-w-2xl grid-cols-1 sm:grid-cols-2 gap-x-8 gap-y-10 lg:mx-0 lg:max-w-none lg:grid-cols-4">

          <article v-for="post in posts" :key="post.id" class="flex flex-col items-start justify-between bg-gray-800 py-5 px-5 rounded-3xl shadow-md shadow-gray-600" >
            <div class="relative w-full cursor-pointer mb-5" @click="openModal(post.imageUrl)">
              <img :src="post.imageUrl" alt="" class="aspect-[16/9] w-full rounded-2xl bg-gray-100 object-cover sm:aspect-[2/1] lg:aspect-[3/2] cursor-pointer"/>
              <div class="absolute inset-0 rounded-2xl ring-1 ring-inset ring-white/10" />
            </div>
            <div class="w-full">
              <div class="group relative">
                <h3 class="mt-4 text-lg font-semibold leading-6 text-white group-hover:text-gray-300 text-center cursor-pointer" @click="openModal(post.imageUrl)">
                  {{ post.title }}
                </h3>
                <p class="mt-4 text-base font-light leading-6 text-white group-hover:text-gray-300 text-center cursor-pointer" @click="openModal(post.imageUrl)">
                  {{ post.title }}
                </p>
              </div>
              <div class="mt-8 flex items-center gap-x-4 text-xs justify-around pb-2">
                <time :datetime="post.datetime" class="text-gray-300">{{ post.date }}</time>
                <a :href="post.category.href" class="relative z-10 rounded-full bg-gray-50 px-3 py-1.5 font-medium text-gray-700 hover:bg-gray-100">{{ post.category.title }}</a>
              </div>
            </div>
          </article>

          <!-- Modal -->
          <div v-show="showModal" class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-75 z-50">
            <div class="w-4/5 relative">
              <img :src="showImageUrl" alt="Imagem" class="max-w-full max-h-full">
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
            title: 'Boost your conversion rate',
            href: '#',
            description:
              'Illo sint voluptas. Error voluptates culpa eligendi. Hic vel totam vitae illo. Non aliquid explicabo necessitatibus unde. Sed exercitationem placeat consectetur nulla deserunt vel. Iusto corrupti dicta.',
            imageUrl:
              'https://lucastrindade.dev/images/certificados/analise-desenvolvimento-de-sistemas.webp',
            date: 'Mar 16, 2023',
            datetime: '2023-03-16',
            category: { title: 'Marketing', href: '#' },
            author: {
              name: 'Michael Foster',
              role: 'Co-Founder / CTO',
              href: '#',
              imageUrl:
                'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
            },
          },
          {
            id: 1,
            title: 'Boost your conversion rate',
            href: '#',
            description:
              'Illo sint voluptas. Error voluptates culpa eligendi. Hic vel totam vitae illo. Non aliquid explicabo necessitatibus unde. Sed exercitationem placeat consectetur nulla deserunt vel. Iusto corrupti dicta.',
            imageUrl:
              'https://lucastrindade.dev/images/certificados/analise-desenvolvimento-de-sistemas.webp',
            date: 'Mar 16, 2023',
            datetime: '2023-03-16',
            category: { title: 'Marketing', href: '#' },
            author: {
              name: 'Michael Foster',
              role: 'Co-Founder / CTO',
              href: '#',
              imageUrl:
                'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
            },
          },
          {
            id: 1,
            title: 'Boost your conversion rate',
            href: '#',
            description:
              'Illo sint voluptas. Error voluptates culpa eligendi. Hic vel totam vitae illo. Non aliquid explicabo necessitatibus unde. Sed exercitationem placeat consectetur nulla deserunt vel. Iusto corrupti dicta.',
            imageUrl:
              'https://lucastrindade.dev/images/certificados/analise-desenvolvimento-de-sistemas.webp',
            date: 'Mar 16, 2023',
            datetime: '2023-03-16',
            category: { title: 'Marketing', href: '#' },
            author: {
              name: 'Michael Foster',
              role: 'Co-Founder / CTO',
              href: '#',
              imageUrl:
                'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
            },
          },
          {
            id: 1,
            title: 'Boost your conversion rate',
            href: '#',
            description:
              'Illo sint voluptas. Error voluptates culpa eligendi. Hic vel totam vitae illo. Non aliquid explicabo necessitatibus unde. Sed exercitationem placeat consectetur nulla deserunt vel. Iusto corrupti dicta.',
            imageUrl:
              'https://lucastrindade.dev/images/certificados/analise-desenvolvimento-de-sistemas.webp',
            date: 'Mar 16, 2023',
            datetime: '2023-03-16',
            category: { title: 'Marketing', href: '#' },
            author: {
              name: 'Michael Foster',
              role: 'Co-Founder / CTO',
              href: '#',
              imageUrl:
                'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
            },
          },
          {
            id: 1,
            title: 'Boost your conversion rate',
            href: '#',
            description:
              'Illo sint voluptas. Error voluptates culpa eligendi. Hic vel totam vitae illo. Non aliquid explicabo necessitatibus unde. Sed exercitationem placeat consectetur nulla deserunt vel. Iusto corrupti dicta.',
            imageUrl:
              'https://lucastrindade.dev/images/certificados/solid-os-5-principios-para-as-boas-praticas-da-poo.webp',
            date: 'Mar 16, 2023',
            datetime: '2023-03-16',
            category: { title: 'Marketing', href: '#' },
            author: {
              name: 'Michael Foster',
              role: 'Co-Founder / CTO',
              href: '#',
              imageUrl:
                'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
            },
          },
          {
            id: 1,
            title: 'Boost your conversion rate',
            href: '#',
            description:
              'Illo sint voluptas. Error voluptates culpa eligendi. Hic vel totam vitae illo. Non aliquid explicabo necessitatibus unde. Sed exercitationem placeat consectetur nulla deserunt vel. Iusto corrupti dicta.',
            imageUrl:
              'https://lucastrindade.dev/images/certificados/vue-js-3.webp',
            date: 'Mar 16, 2023',
            datetime: '2023-03-16',
            category: { title: 'Marketing', href: '#' },
            author: {
              name: 'Michael Foster',
              role: 'Co-Founder / CTO',
              href: '#',
              imageUrl:
                'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
            },
          },
        ],
      };
    },
    methods: {
      handleKeyDown(event) {
      if (event.keyCode === 27) {
        // Pressionada a tecla ESC
        this.closeModal();
      }
    },
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

