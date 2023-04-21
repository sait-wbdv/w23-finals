<script setup>
const props = defineProps({student: {type: Object}});
</script>

<template>
  <figure>
    <img :src="'/images/roster/w23/' + student.avatar" :alt="student.label + ' Profile Pic'">
    <figcaption>
      <aside class="badges">
        <ul>
          <Badge v-for="badge in student.badges" :key="badge.id" :badge=badge>
            <slot></slot>
          </Badge>
        </ul>
      </aside>
      <header>{{student.label}}</header>
      <p>{{student.tagline}}</p>
      <footer class="social">
        <ul>
          <SocialLink v-for="link in student.links" :key="link.id" :link=link>
              <slot></slot>
          </SocialLink>
        </ul>
      </footer>
    </figcaption>
  </figure>
</template>