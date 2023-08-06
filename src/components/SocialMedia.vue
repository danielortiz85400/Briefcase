<!--Social media-->
<template>
    <section class="flex justify-end gap-2 pt-3 pr-6 ">
        <v-btn v-for="({ tooltip, icon }, i) in socialMedia" :key="i" class=" elevation-12" color="grey-lighten-5" size="35"
            :append-icon="icon" variant="tonal">
            <v-tooltip activator="parent" location="bottom">{{ tooltip }}</v-tooltip>
        </v-btn>
    </section>
</template>

<script setup lang="ts">
import { shallowReactive, type DefineComponent } from "vue"
import IconTwitter from './icons/IconTwitter.vue';
import IconGithub from "./icons/IconGithub.vue";

interface SocialMedia {
    tooltip: string
    icon: DefineComponent<{}, {}, {}, {}, {}>
}
const socialMedia: SocialMedia[] = shallowReactive([
    { tooltip: "GitHub", icon: IconGithub },
    { tooltip: "Instagram", icon: IconTwitter },
])
</script>