<!--Currently learning-->
<template>
    <v-timeline side="end" align="start" class="rounded-lg outline outline-purple-100 elevation-16 pa-3" density="compact"
        line-color="white" truncate-line="start">
        <v-timeline-item v-for="(skillsNames, i) in Object.entries(skills)" :key="i" dot-color="grey-darken-3"
            :size="i % 2 === 0 ? 'x-small' : 'small'" density="compact" elevation="14">

            <div class="d-flex text-paragraph">
                <div>
                    <span class="font-medium"> {{ skillsNames[0] }}</span>
                    <div class="d-flex flex-wrap gap-1 pt-1">
                        <v-chip v-for="(props, i) in skillsNames[1]" :key="i" class="elevation-12" :color="props.color"
                            label :prepend-icon="props['prepend-icon']">
                            {{ props.name }}
                        </v-chip>
                    </div>
                </div>
            </div>
        </v-timeline-item>
    </v-timeline>
</template>

<script setup lang="ts">
import { shallowReactive, type DefineComponent } from "vue"
import IconReact from "./icons/IconReact.vue";
import IconNest from "./icons/IconNest.vue";
import IconPrisma from "./icons/IconPrisma.vue";
import IconGraphql from "./icons/IconGraphql.vue";

type SkillNames = {
    [category: string]: {
        name: string
        color: string
        'prepend-icon': DefineComponent<{}, {}, {}, {}, {}>
    }[]
}

const skills: SkillNames = shallowReactive({

    ["Frontend: Frameworks - UI Library "]: [
        { name: "React", color: "red", ['prepend-icon']: IconReact },
    ],
    ["Backend: Frameworks - ORMS"]: [
        { name: "Nest", color: "red", ['prepend-icon']: IconNest },
        { name: "Prisma", color: "indigo-lighten-1", ['prepend-icon']: IconPrisma }
    ],
    ["Database-Manager"]: [
        { name: "GraphQl", color: "pink-accent-3", ['prepend-icon']: IconGraphql }
    ]
})
</script>
