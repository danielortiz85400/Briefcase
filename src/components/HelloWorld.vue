<template>
  <v-card class="card-container outline outline-offset-1 outline-purple-100 rounded-lg bg-grey-darken-4 pa-2">
    <ProfileHeader />
    <SocialMedia />

    <!-- Personal Description-->
    <section class="pa-4">
      <p class="text-paragraph cursor-default">Junior web developer. Self-taught from the world of web application
        development ✨</p>
    </section>
    <PersonalInfo />

    <!--Skills-->
    <v-card flat class="bg-transparent rounded-lg">
      <v-tabs v-model="tab" align-tabs="center" class="text-3d elevation-12 rounded-lg d-inline">
        <v-tab v-for="(item, i) in tabs" :key="i" :value="i">
          {{ item }}
        </v-tab>
      </v-tabs>
      <v-window v-model="tab">
        <v-window-item v-for="(_item, i) in panels" :key="i" :value="i">
          <v-card-text>
            <component :is="panels[i]" />
          </v-card-text>
        </v-window-item>
      </v-window>
    </v-card>
  </v-card>
</template>

<script setup lang="ts">
import { shallowRef, type DefineComponent } from 'vue';
import ProfileHeader from "./ProfileHeader.vue"
import SocialMedia from './SocialMedia.vue';
import PersonalInfo from "./PersonalInfo.vue"
import CurrentSkills from "./CurrentSkills.vue"
import CurrentlyLearning from "./CurrentlyLearning.vue"

// Panels
const tab = shallowRef(null)
const tabs: string[] = ["Skill", "Learning"]
const panels: DefineComponent<{}, {}, {}, {}, {}>[] = [CurrentSkills, CurrentlyLearning]

</script>

<style scoped >
.card-container {
  width: 400px;
  height: 98vh;
}
</style>
