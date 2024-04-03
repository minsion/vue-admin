<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Lightbox</span>
            </li>
        </ul>
        <div>
            <div class="pt-5 space-y-8">
                <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                    <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                        <icon-bell />
                    </div>
                    <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                    ><a href="https://www.npmjs.com/package/vue-easy-lightbox" target="_blank" class="block hover:underline"
                        >https://www.npmjs.com/package/vue-easy-lightbox</a
                    >
                </div>

                <!-- Lightbox -->
                <div class="panel">
                    <h5 class="font-semibold text-lg dark:text-white-light mb-5">Lightbox</h5>
                    <div class="mb-5">
                        <div class="flex mb-5">
                            <div class="ltr:mr-4 rtl:ml-4">
                                <input v-model="allcontrols" :value="true" type="radio" @change="bindFancybox()" class="form-radio mt-1.5" checked />
                            </div>
                            <div class="flex-1">
                                <h4 class="font-semibold text-lg text-primary">All controls</h4>
                                <p class="media-text">Caption, slideshow, thumbnails and fullscreen buttons, tap to toggle controls</p>
                            </div>
                        </div>
                        <div class="flex">
                            <div class="ltr:mr-4 rtl:ml-4">
                                <input v-model="allcontrols" :value="false" type="radio" @change="bindFancybox()" class="form-radio mt-1.5" />
                            </div>
                            <div class="flex-1">
                                <h4 class="font-semibold text-lg text-primary">Minimal</h4>
                                <p class="media-text">No caption, no slideshow, no thumbnails, no fullscreen, tap to close</p>
                            </div>
                        </div>
                        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-3 mt-10">
                            <template v-for="(item, i) in items" :key="i">
                                <a
                                    href="javascript:;"
                                    :class="{ 'md:row-span-2 md:col-span-2': i == 3 }"
                                    @click="
                                        index = i;
                                        visible = true;
                                    "
                                >
                                    <img :src="item.src" alt="image-gallery" class="rounded-md w-full h-full object-cover" />
                                </a>
                            </template>
                            <vue-easy-lightbox
                                :visible="visible"
                                :imgs="items"
                                :index="index"
                                scrollDisabled
                                moveDisabled
                                loop
                                :class="{ minimal: !allcontrols }"
                                @hide="
                                    index = null;
                                    visible = false;
                                "
                            ></vue-easy-lightbox>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import { ref, onMounted } from 'vue';
    import VueEasyLightbox from 'vue-easy-lightbox';
    import { useMeta } from '@/composables/use-meta';

    import IconBell from '@/components/icon/icon-bell.vue';

    useMeta({ title: 'Lightbox' });

    const items: any = ref([]);
    const index: any = ref(null);
    const allcontrols = ref(true);
    const visible = ref(false);

    onMounted(() => {
        bindFancybox();
    });

    const bindFancybox = () => {
        if (allcontrols.value) {
            items.value = [
                {
                    src: '/assets/images/lightbox1.jpg',
                    title: 'This is dummy caption. It has been placed here solely to demonstrate the look and feel of finished, typeset text.',
                    description: 'Photo: Samuel Rohl',
                },
                {
                    src: '/assets/images/lightbox2.jpeg',
                    title: 'This is dummy caption. It has been placed here solely to demonstrate the look and feel of finished, typeset text.',
                    description: 'Photo: Samuel Rohl',
                },
                {
                    src: '/assets/images/lightbox3.jpeg',
                    title: "Dummy caption. It's Greek to you. Unless, of course, you're Greek, in which case, it really makes no sense.",
                    description: 'Photo: Michael Hull',
                },
                {
                    src: '/assets/images/lightbox4.jpeg',
                    title: 'This is dummy caption.',
                    description: 'Photo: Folkert Gorter',
                },
                {
                    src: '/assets/images/lightbox5.jpeg',
                    title: "It's a dummy caption. He who searches for meaning here will be sorely disappointed.",
                    description: 'Photo: Thomas Lefebvre',
                },
                {
                    src: '/assets/images/lightbox6.jpeg',
                    title: "It's a dummy caption. He who searches for meaning here will be sorely disappointed.",
                    description: 'Photo: Thomas Lefebvre',
                },
            ];
        } else {
            items.value = [
                {
                    src: '/assets/images/lightbox1.jpg',
                },
                {
                    src: '/assets/images/lightbox2.jpeg',
                },
                {
                    src: '/assets/images/lightbox3.jpeg',
                },
                {
                    src: '/assets/images/lightbox4.jpeg',
                },
                {
                    src: '/assets/images/lightbox5.jpeg',
                },
                {
                    src: '/assets/images/lightbox6.jpeg',
                },
            ];
        }
    };
</script>
