<script setup lang="ts">
import { shallowReactive } from 'vue';
import IconTwitter from './icons/IconTwitter.vue';
import IconAvailable from "./icons/IconAvailable.vue"
import IconLinks from "./icons/IconLinks.vue"
import IconAugust from "./icons/IconAugust.vue"
import IconJoined from "./icons/IconJoined.vue"
import IconCss from "./icons/IconCss.vue";
import IconJavascript from "./icons/IconJavascript.vue";
import IconVue from "./icons/IconVue.vue";
import IconNode from "./icons/IconNode.vue";
import IconMysql from "./icons/IconMysql.vue";
import IconMongodb from "./icons/IconMongodb.vue";
import IconTypescript from "./icons/IconTypescript.vue";
import IconQuasar from "./icons/IconQuasar.vue";
import IconVuetify from "./icons/IconVuetify.vue";
import IconGithub from "./icons/IconGithub.vue";
import IconNest from "./icons/IconNest.vue";
import IconPrisma from "./icons/IconPrisma.vue";
import IconSass from "./icons/IconSass.vue";
import IconGraphql from "./icons/IconGraphql.vue";


defineProps<{
  msg: string
}>()


const skills = shallowReactive({

  ["Frontend: Frameworks - UI Library "]: [
    { name: "Vue", color: "green-accent-2 ", ['prepend-icon']: IconVue },
    { name: "Sass", color: "pink-lighten-1", ['prepend-icon']: IconSass },
    { name: "Css", color: "light-blue-lighten-1", ['prepend-icon']: IconCss },
    { name: "Typescript", color: "blue-accent-3", ['prepend-icon']: IconTypescript },
    { name: "Quasar", color: "light-blue-accent-3", ['prepend-icon']: IconQuasar },
    { name: "Javascript", color: "yellow", ['prepend-icon']: IconJavascript },
    { name: "Vuetify", color: "blue-lighten-2", ['prepend-icon']: IconVuetify },
  
  ],
  ["Backend: Frameworks - ORMS"]: [
    { name: "Express", color: "green", ['prepend-icon']: IconNode },
    { name: "Nest", color: "red", ['prepend-icon']: IconNest },
    { name: "Prisma", color: "indigo-lighten-1", ['prepend-icon']: IconPrisma }
  ],
  ["Database-Manager"]: [
    { name: "Mysql", color: "blue-darken-4", ['prepend-icon']: IconMysql },
    { name: "MongoDB", color: "", ['prepend-icon']: IconMongodb },
    { name: "GraphQl", color: "pink-accent-3", ['prepend-icon']: IconGraphql }
  ]
})

const badges = shallowReactive([
  { label: true, text: "Avl", ['text-color']: "white", ['prepend-icon']: IconAvailable },
  { label: true, text: "Links", ['text-color']: "white", ['prepend-icon']: IconLinks },
  { label: true, text: "Jun 08", ['text-color']: "white", ['prepend-icon']: IconAugust },
  { label: true, text: "Jan 2021", ['text-color']: "white", ['prepend-icon']: IconJoined }
])

const socialMedia = shallowReactive([
  { tooltip: "GitHub", icon: IconGithub },
  { tooltip: "Instagram", icon: IconTwitter },
])

</script>

<template>
  <v-card class="card-container outline outline-offset-1 outline-purple-100 rounded-lg bg-grey-darken-4 pa-2">
    <!--Header-->
    <header class="bg-gradient relative w-full h-28 outline outline-offset-1 outline-white-500 rounded-lg elevation-12">
      <div
        class="w-full h-full d-flex justify-center align-top rounded-lg backdrop-blur-md bg-white/10 text-5xl text-white p-2">

        <div class="cursor-default text-center">
          <v-btn class="text-paragraph px-2 rounded-xl elevation-12 " color="#FF1744" size="small" variant="tonal">
            @ZeroCool
          </v-btn>
        </div>
        <span class="text-3d cursor-default text-center "> Daniel Ortiz</span>
      </div>
      <div class="w-28 h-28 absolute bottom-0 left-0 translate-y-1/2">
        <v-img class="rounded-full  border-double border-8 border-white-500"
          src="https://ih1.redbubble.net/image.3876842807.7930/st,small,507x507-pad,600x600,f8f8f8.jpg" width="200"
          height="200" loading="eager">
          <template v-slot:placeholder>
            <div class="d-flex align-center justify-center fill-height">
              <v-progress-circular color="grey-lighten-4" indeterminate></v-progress-circular>
            </div>
          </template>
        </v-img>
      </div>
    </header>
    <!--Redes sociales!-->
    <section class="flex justify-end gap-2 pt-3 pr-6 ">
      <v-btn v-for="({ tooltip, icon }, i) in socialMedia" :key="i" class=" elevation-12" color="grey-lighten-5" size="35"
        :append-icon="icon" variant="tonal">
        <v-tooltip activator="parent" location="bottom">{{ tooltip }}</v-tooltip>
      </v-btn>
    </section>

    <!-- Descripción personal-->
    <section class="pt-5">
      <p class="text-paragraph cursor-default mb-2">Brings ideas to life with code! ✨</p>
      <p class="text-paragraph cursor-default">Junior web developer. Self-taught from the world of web application
        development.</p>
    </section>
    <!--Información personal-->
    <section class="d-flex justify-center rounded-lg outline elevation-18 gap-2 my-2 p-2">
      <v-chip v-for="(props, i) in badges" :key="i" class="text-paragraph elevation-16 backdrop-blur-lg" color="white"
        :label="props.label" :text-color="props['text-color']" variant="outlined" :prepend-icon="props['prepend-icon']">
        {{ props.text }}
        <v-badge v-if="props.text === 'Avl'" dot color="light-green-accent-3" class="absolute top-1 right-1">
          <v-tooltip activator="parent" location="bottom">Available! ✍🏻</v-tooltip>
        </v-badge>
      </v-chip>
    </section>

    <!--Hábilidades-->
    <v-card class="bg-transparent pt-4 pa-3 rounded-lg">
      <div class="text-center"> <v-card-title
          class="text-3d bg-gradient elevation-12 cursor-default d-inline rounded-lg outline outline-offset-1 outline-white-500 pa-0 px-2">Skills:</v-card-title>
      </div>
      <v-timeline side="end" align="start" class="rounded-lg outline elevation-16 mt-4 pa-4" density="compact"
        line-color="white" truncate-line="start">
        <v-timeline-item v-for="(skillsNames, i) in Object.entries(skills)" :key="i" dot-color="grey-darken-3"
          :size="i % 2 === 0 ? 'x-small' : 'small'" density="compact" elevation="14">

          <div class="d-flex">
            <div class="text-paragraph">
              <span class="font-medium"> {{ skillsNames[0] }}</span>
              <div class="d-flex flex-wrap text-caption gap-1">

                <v-chip v-for="(props, i) in skillsNames[1]" :key="i" class="text-paragraph elevation-12"
                  :color="props.color" label :prepend-icon="props['prepend-icon']">
                  {{ props.name }}
                </v-chip>
              </div>
            </div>
          </div>
        </v-timeline-item>
      </v-timeline>
    </v-card>
  </v-card>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Slackey&display=swap");
@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap');

.card-container {
  width: 400px;
  height: 98vh;
}

.bg-gradient {
  background-image: linear-gradient(to right, #ECE9E6 0%, #FFFFFF 51%, #ECE9E6 100%);
  background-size: 200% auto;
  transition: 0.5s;
}

.bg-gradient:hover {
  background-position: right center;
  color: #fff;
  text-decoration: none;
}

.text-3d {
  font-family: "Slackey", cursive;
  text-shadow: 0 1px 0 #ccc, 0 2px 0 #c9c9c9, 0 3px 0 #bbb, 0 4px 0 #b9b9b9,
    0 5px 0 #aaa, 0 6px 1px rgba(0, 0, 0, 0.1), 0 0 5px rgba(0, 0, 0, 0.1),
    0 1px 3px rgba(0, 0, 0, 0.3), 0 3px 5px rgba(0, 0, 0, 0.2),
    0 5px 10px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.2),
    0 20px 20px rgba(0, 0, 0, 0.15), 0 20px 30px rgba(0, 0, 0, 0.15);
  -webkit-text-stroke: 0.4px rgba(36, 48, 132, 0.4);
}

.text-paragraph {
  font-family: 'Share Tech Mono', monospace;
  font-weight: 500;
}

/*h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}*/
</style>
