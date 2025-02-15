<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <section class="bg-white">
    <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
      <div class="sm:flex sm:flex-col sm:align-center">
        <h1 class="text-5xl font-extrabold text-gray-900 sm:text-center">
          Bootcamps
        </h1>
        <p class="mt-5 text-xl text-gray-500 sm:text-center">
          Our courses are designed to turn complete beginners into professional
          web developers.
        </p>
        <div
          class="
            relative
            self-center
            mt-6
            bg-gray-100
            rounded-lg
            p-0.5
            flex
            sm:mt-8
          "
        ></div>
      </div>
      <div
        class="
          mt-12
          space-y-4
          sm:mt-16
          sm:space-y-0
          sm:grid sm:grid-cols-2
          sm:gap-6
          lg:max-w-4xl
          lg:mx-auto
          xl:max-w-none
          xl:mx-0
          xl:grid-cols-4
        "
      >
        <figure
          v-for="course in courses"
          :key="course.name"
          class="
            border border-gray-200
            rounded-lg
            shadow-sm
            divide-y divide-gray-200
          "
        >
          <div class="p-6">
            <h2 class="text-lg leading-6 font-medium text-gray-900">
              {{ course.name }}
            </h2>
            <p class="mt-4 text-sm text-gray-500 description">
              {{ course.description }}
            </p>
            <p v-if="course[101]" class="mt-8 text-base">Every 2 weeks</p>
            <p v-else class="mt-8">
              Next course:
              <span class="text-base font-extrabold text-gray-900">{{
                course.nextCourse
              }}</span>
            </p>
            <nuxt-link
              :to="course.href"
              class="
                mt-8
                block
                w-full
                bg-orange-600
                border border-orange-600
                rounded-md
                py-2
                text-sm
                font-semibold
                text-white text-center
                hover:bg-orange-700
              "
              >{{ course.buttonText }}</nuxt-link
            >
          </div>
          <div class="pt-6 pb-8 px-6">
            <h3
              class="text-xs font-medium text-gray-900 tracking-wide uppercase"
            >
              Features
            </h3>
            <ul class="mt-6 space-y-4">
              <li
                v-for="tidbit in course.info"
                :key="tidbit"
                class="flex space-x-3"
              >
                <CheckIcon
                  class="flex-shrink-0 h-5 w-5 text-orange-500"
                  aria-hidden="true"
                />
                <span class="text-sm text-gray-500">{{ tidbit }}</span>
              </li>
            </ul>
          </div>
        </figure>
      </div>
    </div>
  </section>
</template>

<script>
import CheckIcon from '~/components/heroicons/CheckIcon.vue'
export default {
  components: {
    CheckIcon,
  },
  props: ['courses'],
}
</script>
<style scoped>
@media (min-width: 1024px) {
  .description {
    height: 120px;
  }
}
</style>
