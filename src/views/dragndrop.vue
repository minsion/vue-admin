<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse mb-6">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Dashboard</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Drag & Drop</span>
            </li>
        </ul>

        <div class="dragndrop space-y-8">
            <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                    <icon-bell />
                </div>
                <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                ><a href="https://www.npmjs.com/package/vue-draggable-next" target="_blank" class="block hover:underline"
                    >https://www.npmjs.com/package/vue-draggable-next</a
                >
            </div>

            <!-- Sortable -->
            <div class="panel">
                <div class="font-semibold text-lg mb-5">Sortable</div>
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-x-12">
                    <div>
                        <ul>
                            <draggable group="shared" ghost-class="gu-transit" :animation="200">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:md:text-left rtl:md:text-right text-center items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id}.jpeg`" class="w-11 h-11 rounded-full mx-auto" />
                                            </div>
                                            <div class="flex md:flex-row flex-col justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                                <div>
                                                    <button type="button" class="btn btn-secondary btn-sm px-5 py-2">View</button>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>

                    <div>
                        <ul>
                            <draggable group="shared" ghost-class="gu-transit" :animation="200">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:md:text-left rtl:md:text-right text-center items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id + 5}.jpeg`" class="w-11 h-11 rounded-full mx-auto" />
                                            </div>
                                            <div class="flex md:flex-row flex-col justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                                <div>
                                                    <button type="button" class="btn btn-secondary btn-sm px-5 py-2">View</button>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- Icon Change -->
            <div class="panel">
                <div class="font-semibold text-lg dark:text-white mb-5">Icon Change</div>
                <div class="icon-change grid grid-cols-1 sm:grid-cols-2 gap-x-12">
                    <div>
                        <ul class="left">
                            <draggable group="icon" ghost-class="gu-transit" :animation="200">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:text-left rtl:text-right items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id}.jpeg`" class="w-11 h-11 rounded-full" />
                                            </div>
                                            <div class="flex justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                                <div class="text-white-dark">
                                                    <icon-star class="w-6 h-6 feather-star" />
                                                    <icon-heart class="feather-heart" />
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>

                    <div>
                        <ul class="right">
                            <draggable group="icon" ghost-class="gu-transit" :animation="200">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:text-left rtl:text-right items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id + 5}.jpeg`" class="w-11 h-11 rounded-full" />
                                            </div>
                                            <div class="flex justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                                <div class="text-white-dark">
                                                    <icon-star class="w-6 h-6 feather-star" />
                                                    <icon-heart class="feather-heart" />
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- Handler -->
            <div class="panel">
                <div class="font-semibold text-lg dark:text-white mb-5">Handler</div>
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-x-12">
                    <div>
                        <ul>
                            <draggable group="handler" ghost-class="gu-transit" handle=".handle" :animation="200">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:md:text-left rtl:md:text-right text-center items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id}.jpeg`" class="w-11 h-11 rounded-full mx-auto" />
                                            </div>
                                            <div class="sm:flex block justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                                <div class="text-white-dark">
                                                    <span class="handle px-2 ltr:mr-1 rtl:ml-1 bg-[#ebedf2] dark:bg-black rounded cursor-move">+</span>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>

                    <div>
                        <ul>
                            <draggable group="handler" ghost-class="gu-transit" handle=".handle" :animation="200">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:md:text-left rtl:md:text-right text-center items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id + 5}.jpeg`" class="w-11 h-11 rounded-full mx-auto" />
                                            </div>
                                            <div class="sm:flex block justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                                <div class="text-white-dark">
                                                    <span class="handle px-2 ltr:mr-1 rtl:ml-1 bg-[#ebedf2] dark:bg-black rounded cursor-move">+</span>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- News feed -->
            <div class="panel">
                <div class="font-semibold text-lg dark:text-white mb-5">News Feed</div>
                <div>
                    <draggable group="newsfeed" :animation="200" class="grid grid-cols-1 sm:grid-cols-2 gap-x-12">
                        <template v-for="(item, i) in items" :key="i">
                            <div class="mb-2.5" v-show="item.id <= 4">
                                <div class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5">
                                    <div class="py-sm-2.5 sm:flex block ltr:md:text-left rtl:md:text-right text-center items-md-center">
                                        <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                            <img alt="avatar" :src="`/assets/images/profile-${item.id + 1}.jpeg`" class="w-11 h-11 rounded-lg mx-auto" />
                                        </div>
                                        <div class="flex md:flex-row flex-col justify-between items-center flex-1">
                                            <div class="font-semibold md:my-0 my-3">
                                                <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.name }}</div>
                                                <div class="text-white-dark text-xs">11 hours ago</div>
                                            </div>
                                        </div>
                                    </div>
                                    <div class="py-5 border-b border-b-[#f1f2f3] dark:border-b-dark mb-4">
                                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                        aliqua. Ut enim ad minim veniam, quis nostrud exercitation.
                                    </div>
                                    <div class="md:flex items-center flex-wrap">
                                        <div class="ltr:md:text-left rtl:md:text-right text-center xl:flex-1">
                                            <div class="flex md:justify-start justify-center -space-x-2 rtl:space-x-reverse text-white">
                                                <img
                                                    class="w-10 h-10 rounded-full object-cover ring-2 ring-white dark:ring-white-dark"
                                                    src="/assets/images/profile-6.jpeg"
                                                    alt=""
                                                />
                                                <img
                                                    class="w-10 h-10 rounded-full object-cover ring-2 ring-white dark:ring-white-dark"
                                                    src="/assets/images/profile-7.jpeg"
                                                    alt=""
                                                />
                                                <img
                                                    class="w-10 h-10 rounded-full object-cover ring-2 ring-white dark:ring-white-dark"
                                                    src="/assets/images/profile-8.jpeg"
                                                    alt=""
                                                />
                                                <img
                                                    class="w-10 h-10 rounded-full object-cover ring-2 ring-white dark:ring-white-dark"
                                                    src="/assets/images/profile-10.jpeg"
                                                    alt=""
                                                />
                                            </div>
                                        </div>
                                        <div class="ltr:md:text-right rtl:md:text-left text-center">
                                            <span class="text-xs text-white-dark lg:pt-0 pt-2 block"
                                                ><a href="javascript:;" class="text-danger dark:text-primary font-semibold text-sm">Vincent, Mary</a> and 19
                                                other like this</span
                                            >
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </template>
                    </draggable>
                </div>
            </div>

            <!-- Delete User -->
            <div class="panel">
                <div class="font-semibold text-lg dark:text-white mb-5">Delete User</div>
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-x-12">
                    <div>
                        <ul>
                            <draggable group="delete" ghost-class="gu-transit" removeOnSpill="true" :animation="200" class="min-h-[200px]">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:md:text-left rtl:md:text-right text-center items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id}.jpeg`" class="w-11 h-11 rounded-full mx-auto" />
                                            </div>
                                            <div class="flex md:flex-row flex-col justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>

                    <div>
                        <ul>
                            <draggable group="delete" ghost-class="gu-transit" removeOnSpill="true" :animation="200" class="min-h-[200px]">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:md:text-left rtl:md:text-right text-center items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id + 5}.jpeg`" class="w-11 h-11 rounded-full mx-auto" />
                                            </div>
                                            <div class="flex md:flex-row flex-col justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- Grid drag -->
            <div class="panel">
                <div class="font-semibold text-lg dark:text-white mb-5">Grid drag</div>
                <div>
                    <draggable group="grid" :animation="200" class="grid grid-cols-2 sm:grid-cols-4 md:grid-cols-6 xl:grid-cols-8 gap-8 place-items-center">
                        <template v-for="i in 12" :key="i">
                            <div
                                class="w-24 h-24 border border-white-light rounded-md shadow dark:border-dark flex items-center justify-center font-semibold cursor-grab"
                            >
                                {{ 'Item ' + i }}
                            </div>
                        </template>
                    </draggable>
                </div>
            </div>

            <!-- Swap -->
            <div class="panel">
                <div class="font-semibold text-lg dark:text-white mb-5">Swap</div>
                <div>
                    <div>
                        <ul>
                            <draggable swap="true" :animation="200" swapThreshold="1" class="grid grid-cols-1 lg:grid-cols-2 gap-x-12">
                                <template v-for="(item, i) in items" :key="i">
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:md:text-left rtl:md:text-right text-center items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id}.jpeg`" class="w-11 h-11 rounded-full mx-auto" />
                                            </div>
                                            <div class="flex md:flex-row flex-col justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                    <li class="mb-2.5 cursor-grab">
                                        <div
                                            class="bg-white dark:bg-[#1b2e4b] rounded-md border border-white-light dark:border-dark px-6 py-3.5 flex md:flex-row flex-col ltr:md:text-left rtl:md:text-right text-center items-md-center"
                                        >
                                            <div class="ltr:sm:mr-4 rtl:sm:ml-4">
                                                <img alt="avatar" :src="`/assets/images/profile-${item.id + 5}.jpeg`" class="w-11 h-11 rounded-full mx-auto" />
                                            </div>
                                            <div class="flex md:flex-row flex-col justify-between items-center flex-1">
                                                <div class="font-semibold md:my-0 my-3">
                                                    <div class="text-dark dark:text-[#bfc9d4] text-base">{{ item.text }}</div>
                                                    <div class="text-white-dark text-xs">{{ item.name }}</div>
                                                </div>
                                            </div>
                                        </div>
                                    </li>
                                </template>
                            </draggable>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import { ref } from 'vue';
    import { VueDraggableNext as draggable } from 'vue-draggable-next';
    import { useMeta } from '@/composables/use-meta';

    import IconBell from '@/components/icon/icon-bell.vue';
    import IconStar from '@/components/icon/icon-star.vue';
    import IconHeart from '@/components/icon/icon-heart.vue';

    useMeta({ title: 'Drag & Drop' });

    const items = ref([
        {
            id: 1,
            text: 'Need to be approved',
            name: 'Kelly Young',
        },
        {
            id: 2,
            text: 'Meeting with client',
            name: 'Andy King',
        },
        {
            id: 3,
            text: 'Project Detail',
            name: 'Judy Holmes',
        },
        {
            id: 4,
            text: 'Edited Post Apporval',
            name: 'Vincent Carpenter',
        },
        {
            id: 5,
            text: 'Project Lead Pickup',
            name: 'Mary McDonald',
        },
    ]);
</script>
