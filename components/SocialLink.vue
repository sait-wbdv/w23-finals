<script setup>
const props = defineProps({link: {type: Object}});

const socialLookUp = {
  homepage: 'fa6-solid:house-chimney',
  github: 'fa6-brands:github',
  codepen: 'fa6-brands:codepen',
  linkedin: 'fa6-brands:linkedin',
  facebook: 'fa6-brands:square-facebook',
  instagram: 'fa6-brands:instagram',
  youtube: 'fa6-brands:youtube',
  email: 'fa6-regular:envelope',
  resume: 'fa6-regular:file-lines',
  default: 'fa6-solid:user-tie'
}
</script>

<template>
  <li>
    <a :href="link.link" target="_blank"><Icon :name="socialLookUp[link.label]"></Icon></a>
  </li>
</template>