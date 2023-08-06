<!--Personal info-->
<template>
    <section class="d-flex justify-center rounded-lg outline outline-purple-100  elevation-18 gap-2 my-1 mx-3 p-2">
        <v-chip v-for="(props, i) in badges" :key="i" class="text-paragraph elevation-16 backdrop-blur-lg" color="white"
            :label="props.label" text-color="white" variant="outlined" :prepend-icon="props['prepend-icon']">
            {{ props.text }}
            <v-badge v-if="props.text === 'Avl'" dot color="light-green-accent-3" class="absolute top-1 right-1">
                <v-tooltip activator="parent" location="bottom">Available! ✍🏻</v-tooltip>
            </v-badge>
        </v-chip>
    </section>
</template>

<script setup lang="ts">
import { shallowReactive, type DefineComponent } from "vue"
import IconAvailable from "./icons/IconAvailable.vue"
import IconLinks from "./icons/IconLinks.vue"
import IconAugust from "./icons/IconAugust.vue"
import IconJoined from "./icons/IconJoined.vue"

interface Badges {
    label: boolean
    text: string
    'prepend-icon': DefineComponent<{}, {}, {}, {}, {}>
}

const badges: Badges[] = shallowReactive([
    { label: true, text: "Avl", ['prepend-icon']: IconAvailable },
    { label: true, text: "Links", ['prepend-icon']: IconLinks },
    { label: true, text: "Jun 08", ['prepend-icon']: IconAugust },
    { label: true, text: "Jan 2021", ['prepend-icon']: IconJoined }
])
</script>