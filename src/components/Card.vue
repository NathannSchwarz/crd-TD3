<script setup lang="ts">
import DuotoneImg from '@/components/DuotoneImg.vue'
const props = defineProps<{
  id: number
  title: string
  date: string
  excerpt: string
  imgCardPath: string
  imgAlt?: string
}>()
</script>
<template>
  <article
    class="group col-span-4 grid grid-cols-[24px_1fr] grid-rows-[200px_48px_1fr] lg:grid-cols-[2fr_11fr]"
  >
    <DuotoneImg
      :imgPath="imgCardPath"
      :imgAlt="imgAlt"
      classPicture="col-span-2 col-start-1 row-span-2 row-start-1 group-hover:bg-black"
      classImg="group-hover:grayscale-0 group-hover:mix-blend-normal"
    />
    <h3 class="col-start-2 row-start-1 z-[1] my-6 mr-4 text-white text-3xl self-end">
      <a href="#">{{ title }}</a>
    </h3>
    <div class="bg-white col-start-2 row-start-2 row-span-2 p-6 z-[2] space-y-4">
      <p class="uppercase">{{ date }}</p>
      <p>{{ excerpt }}</p>
      <a class="uppercase inline-block border-b-2 border-black" href="#">Plus d'info</a>
    </div>
  </article>
</template>
