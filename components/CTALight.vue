<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <div class="bg-orange-100">
    <div
      class="
        max-w-7xl
        mx-auto
        py-12
        px-4
        sm:px-6
        lg:py-24
        lg:px-8
        lg:flex
        lg:items-center
        lg:justify-between
      "
    >
      <h2
        class="text-3xl font-extrabold tracking-tight text-gray-900 md:text-4xl"
      >
        <span class="block">{{ line1 }}</span>
        <span class="block text-orange-600">{{ line2 }}</span>
      </h2>
      <div class="mt-8 flex lg:mt-0 lg:flex-shrink-0">
        <div class="inline-flex rounded-md shadow">
          <nuxt-link
            :to="href"
            class="
              inline-flex
              items-center
              justify-center
              px-5
              py-3
              border border-transparent
              text-base
              font-medium
              rounded-md
              text-white
              bg-orange-600
              hover:bg-orange-700
            "
          >
            {{ buttonText }}
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ['line1', 'line2', 'buttonText', 'href'],
}
</script>
