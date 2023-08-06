<!--Profile header-->
<template>
    <header class="bg-gradient relative w-full h-28 outline outline-offset-1 outline-purple-100 rounded-lg elevation-12">
        <div
            class="w-full h-full d-flex justify-center align-top rounded-lg backdrop-blur-md bg-white/10 text-5xl text-white p-2">

            <div class="cursor-default text-center">
                <v-btn class="text-paragraph px-2 rounded-xl elevation-12 " color="deep-purple-accent-3
" size="small" variant="tonal">
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
</template>
