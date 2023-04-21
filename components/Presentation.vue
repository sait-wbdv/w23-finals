<script setup>
import { roster } from '../data/roster-w23';

const props = defineProps({
  round: {type: Object},
  index: {type: Number}
});
</script>

<template>
  <h3 class="rounds open">Presentations: {{round.start}}</h3>
  <!-- <h3 class="rounds open">{{round.start}}: Round {{(index + 1)}} Presentations</h3> -->
      <section :id="round.container">
        <article class="presentation" v-for="speaker in round.speakers" :key="speaker.id" :speaker=speaker>
          <header><h4>{{speaker.title}}</h4></header>
          <div>
            <ul>
              <li v-if="!speaker.members">
                <RosterCard :student="roster.find(item => item.label === speaker.name)">
                  <slot></slot>
                </RosterCard>
              </li>
              <li v-else v-for="student in speaker.members" :key="student.id">
                <RosterCard :student="roster.find(item => item.label === student)">
                  <slot></slot>
                </RosterCard>
              </li>
            </ul>
          </div>
        </article>
      </section>
</template>
