<template>
    <div>
        <div class="flex gap-5 relative sm:h-[calc(100vh_-_150px)] h-full">
            <div
                class="bg-black/60 z-10 w-full h-full rounded-md absolute hidden"
                :class="{ '!block xl:!hidden': isShowNoteMenu }"
                @click="isShowNoteMenu = !isShowNoteMenu"
            ></div>
            <div
                class="panel p-4 flex-none w-[240px] absolute xl:relative z-10 space-y-4 h-full xl:h-auto hidden xl:block ltr:lg:rounded-r-md ltr:rounded-r-none rtl:lg:rounded-l-md rtl:rounded-l-none overflow-hidden"
                :class="{ 'hidden shadow': !isShowNoteMenu, '!block h-full ltr:left-0 rtl:right-0': isShowNoteMenu }"
            >
                <div class="flex flex-col h-full pb-16">
                    <div class="flex text-center items-center">
                        <div class="shrink-0">
                            <icon-notes />
                        </div>
                        <h3 class="text-lg font-semibold ltr:ml-3 rtl:mr-3">Notes</h3>
                    </div>
                    <div class="h-px w-full border-b border-[#e0e6ed] dark:border-[#1b2e4b] my-4"></div>
                    <perfect-scrollbar
                        :options="{
                            swipeEasing: true,
                            wheelPropagation: false,
                        }"
                        class="relative ltr:pr-3.5 rtl:pl-3.5 ltr:-mr-3.5 rtl:-ml-3.5 h-full grow"
                    >
                        <div class="space-y-1">
                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{ 'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': selectedTab === 'all' }"
                                @click="tabChanged('all')"
                            >
                                <div class="flex items-center">
                                    <icon-notes-edit class="shrink-0" />

                                    <div class="ltr:ml-3 rtl:mr-3">All Notes</div>
                                </div>
                            </button>
                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{ 'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': selectedTab === 'fav' }"
                                @click="tabChanged('fav')"
                            >
                                <div class="flex items-center">
                                    <icon-star class="shrink-0" />
                                    <div class="ltr:ml-3 rtl:mr-3">Favourites</div>
                                </div>
                            </button>
                            <div class="h-px w-full border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>
                            <div class="px-1 py-3 text-white-dark">Tags</div>
                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-primary ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'personal' }"
                                @click="tabChanged('personal')"
                            >
                                <icon-square-rotated class="fill-primary shrink-0" />

                                <div class="ltr:ml-3 rtl:mr-3">Personal</div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-warning ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'work' }"
                                @click="tabChanged('work')"
                            >
                                <icon-square-rotated class="fill-warning shrink-0" />
                                <div class="ltr:ml-3 rtl:mr-3">Work</div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-info ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'social' }"
                                @click="tabChanged('social')"
                            >
                                <icon-square-rotated class="fill-info shrink-0" />
                                <div class="ltr:ml-3 rtl:mr-3">Social</div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-danger ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'important' }"
                                @click="tabChanged('important')"
                            >
                                <icon-square-rotated class="fill-danger shrink-0" />
                                <div class="ltr:ml-3 rtl:mr-3">Important</div>
                            </button>
                        </div>
                    </perfect-scrollbar>
                </div>
                <div class="ltr:left-0 rtl:right-0 absolute bottom-0 p-4 w-full">
                    <button class="btn btn-primary w-full" type="button" @click="editNote()">
                        <icon-plus class="w-5 h-5 ltr:mr-2 rtl:ml-2 shrink-0" />
                        Add New Note
                    </button>
                </div>
            </div>

            <div class="panel flex-1 overflow-auto h-full">
                <div class="pb-5">
                    <button type="button" class="xl:hidden hover:text-primary" @click="isShowNoteMenu = !isShowNoteMenu">
                        <icon-menu />
                    </button>
                </div>
                <template v-if="!filterdNotesList.length">
                    <div class="flex justify-center items-center sm:min-h-[300px] min-h-[400px] font-semibold text-lg h-full">No data available</div>
                </template>
                <template v-if="filterdNotesList.length">
                    <div class="sm:min-h-[300px] min-h-[400px]">
                        <div class="grid 2xl:grid-cols-4 lg:grid-cols-3 sm:grid-cols-2 grid-cols-1 gap-5">
                            <template v-for="note in filterdNotesList" :key="note.id">
                                <div
                                    class="panel pb-12"
                                    :class="{
                                        'bg-primary-light shadow-primary': note.tag === 'personal',
                                        'bg-warning-light shadow-warning': note.tag === 'work',
                                        'bg-info-light shadow-info': note.tag === 'social',
                                        'bg-danger-light shadow-danger': note.tag === 'important',
                                        'dark:shadow-dark': !note.tag,
                                    }"
                                >
                                    <div class="min-h-[142px]">
                                        <div class="flex justify-between">
                                            <div class="flex items-center w-max">
                                                <div class="flex-none">
                                                    <div v-if="note.thumb" class="p-0.5 bg-gray-300 dark:bg-gray-700 rounded-full">
                                                        <img class="h-8 w-8 rounded-full object-cover" :src="`/assets/images/${note.thumb}`" />
                                                    </div>
                                                    <div
                                                        v-if="!note.thumb && note.user"
                                                        class="grid place-content-center h-8 w-8 rounded-full bg-gray-300 dark:bg-gray-700 text-sm font-semibold"
                                                    >
                                                        {{ note.user.charAt(0) + '' + note.user.charAt(note.user.indexOf('') + 1) }}
                                                    </div>
                                                    <div
                                                        v-if="!note.thumb && !note.user"
                                                        class="bg-gray-300 dark:bg-gray-700 rounded-full grid place-content-center h-8 w-8"
                                                    >
                                                        <icon-user class="w-4.5 h-4.5" />
                                                    </div>
                                                </div>
                                                <div class="ltr:ml-2 rtl:mr-2">
                                                    <div class="font-semibold">{{ note.user }}</div>
                                                    <div class="text-sx text-white-dark">{{ note.date }}</div>
                                                </div>
                                            </div>
                                            <div class="dropdown">
                                                <Popper :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'" offsetDistance="0">
                                                    <button type="button" class="text-primary">
                                                        <icon-horizontal-dots class="rotate-90 opacity-70 hover:opacity-100" />
                                                    </button>
                                                    <template #content="{ close }">
                                                        <ul @click="close()" class="text-sm font-medium">
                                                            <li>
                                                                <a href="javascript:;" class="w-full" @click="editNote(note)">
                                                                    <icon-pencil class="w-4 h-4 ltr:mr-3 rtl:ml-3 shrink-0" />

                                                                    Edit
                                                                </a>
                                                            </li>
                                                            <li>
                                                                <a href="javascript:;" class="w-full" @click="deleteNoteConfirm(note)">
                                                                    <icon-trash-lines class="w-4.5 h-4.5 ltr:mr-3 rtl:ml-3 shrink-0" />
                                                                    Delete
                                                                </a>
                                                            </li>
                                                            <li>
                                                                <a href="javascript:;" class="w-full" @click="viewNote(note)">
                                                                    <icon-eye class="w-4.5 h-4.5 ltr:mr-3 rtl:ml-3 shrink-0" />

                                                                    View
                                                                </a>
                                                            </li>
                                                        </ul>
                                                    </template>
                                                </Popper>
                                            </div>
                                        </div>
                                        <div>
                                            <h4 class="font-semibold mt-4">{{ note.title }}</h4>
                                            <p class="text-white-dark mt-2">{{ note.description }}</p>
                                        </div>
                                    </div>
                                    <div class="absolute bottom-5 left-0 w-full px-5">
                                        <div class="flex items-center justify-between mt-2">
                                            <div class="dropdown">
                                                <Popper :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'" offsetDistance="0">
                                                    <button
                                                        type="button"
                                                        :class="{
                                                            'text-primary': note.tag === 'personal',
                                                            'text-warning': note.tag === 'work',
                                                            'text-info': note.tag === 'social',
                                                            'text-danger': note.tag === 'important',
                                                        }"
                                                    >
                                                        <icon-square-rotated
                                                            :class="{
                                                                'fill-primary': note.tag === 'personal',
                                                                'fill-warning': note.tag === 'work',
                                                                'fill-info': note.tag === 'social',
                                                                'fill-danger': note.tag === 'important',
                                                            }"
                                                        />
                                                    </button>
                                                    <template #content="{ close }">
                                                        <ul @click="close()">
                                                            <li>
                                                                <a href="javascript:;" @click="setTag(note, 'personal')">
                                                                    <icon-square-rotated class="ltr:mr-2 rtl:ml-2 fill-primary text-primary" />
                                                                    Personal
                                                                </a>
                                                            </li>
                                                            <li>
                                                                <a href="javascript:;" @click="setTag(note, 'work')">
                                                                    <icon-square-rotated class="ltr:mr-2 rtl:ml-2 fill-warning text-warning" />
                                                                    Work
                                                                </a>
                                                            </li>
                                                            <li>
                                                                <a href="javascript:;" @click="setTag(note, 'social')">
                                                                    <icon-square-rotated class="ltr:mr-2 rtl:ml-2 fill-info text-info" />
                                                                    Social
                                                                </a>
                                                            </li>
                                                            <li>
                                                                <a href="javascript:;" @click="setTag(note, 'important')">
                                                                    <icon-square-rotated class="ltr:mr-2 rtl:ml-2 fill-danger text-danger" />
                                                                    Important
                                                                </a>
                                                            </li>
                                                        </ul>
                                                    </template>
                                                </Popper>
                                            </div>
                                            <div class="flex items-center">
                                                <button type="button" class="text-danger" @click="deleteNoteConfirm(note)">
                                                    <icon-trash-lines />
                                                </button>
                                                <button type="button" class="text-warning group ltr:ml-2 rtl:mr-2" @click="setFav(note)">
                                                    <icon-star class="w-4.5 h-4.5 group-hover:fill-warning" :class="{ 'fill-warning': note.isFav }" />
                                                </button>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </template>
                        </div>
                    </div>
                </template>

                <TransitionRoot appear :show="isAddNoteModal" as="template">
                    <Dialog as="div" @close="isAddNoteModal = false" class="relative z-[51]">
                        <TransitionChild
                            as="template"
                            enter="duration-300 ease-out"
                            enter-from="opacity-0"
                            enter-to="opacity-100"
                            leave="duration-200 ease-in"
                            leave-from="opacity-100"
                            leave-to="opacity-0"
                        >
                            <DialogOverlay class="fixed inset-0 bg-[black]/60" />
                        </TransitionChild>

                        <div class="fixed inset-0 overflow-y-auto">
                            <div class="flex min-h-full items-center justify-center px-4 py-8">
                                <TransitionChild
                                    as="template"
                                    enter="duration-300 ease-out"
                                    enter-from="opacity-0 scale-95"
                                    enter-to="opacity-100 scale-100"
                                    leave="duration-200 ease-in"
                                    leave-from="opacity-100 scale-100"
                                    leave-to="opacity-0 scale-95"
                                >
                                    <DialogPanel class="panel border-0 p-0 rounded-lg overflow-hidden w-full max-w-lg text-black dark:text-white-dark">
                                        <button
                                            type="button"
                                            class="absolute top-4 ltr:right-4 rtl:left-4 text-gray-400 hover:text-gray-800 dark:hover:text-gray-600 outline-none"
                                            @click="isAddNoteModal = false"
                                        >
                                            <icon-x />
                                        </button>
                                        <div class="text-lg font-medium bg-[#fbfbfb] dark:bg-[#121c2c] ltr:pl-5 rtl:pr-5 py-3 ltr:pr-[50px] rtl:pl-[50px]">
                                            {{ params.id ? 'Edit Note' : 'Add Note' }}
                                        </div>
                                        <div class="p-5">
                                            <form @submit.prevent="saveNote">
                                                <div class="mb-5">
                                                    <label for="title">Title</label>
                                                    <input id="title" type="text" placeholder="Enter Title" class="form-input" v-model="params.title" />
                                                </div>
                                                <div class="mb-5">
                                                    <label for="name">User Name</label>
                                                    <select id="name" class="form-select" v-model="params.user">
                                                        <option value="">Select User</option>
                                                        <option value="Max Smith">Max Smith</option>
                                                        <option value="John Doe">John Doe</option>
                                                        <option value="Kia Jain">Kia Jain</option>
                                                        <option value="Karena Courtliff">Karena Courtliff</option>
                                                        <option value="Vladamir Koschek">Vladamir Koschek</option>
                                                        <option value="Robert Garcia">Robert Garcia</option>
                                                        <option value="Marie Hamilton">Marie Hamilton</option>
                                                        <option value="Megan Meyers">Megan Meyers</option>
                                                        <option value="Angela Hull">Angela Hull</option>
                                                        <option value="Karen Wolf">Karen Wolf</option>
                                                        <option value="Jasmine Barnes">Jasmine Barnes</option>
                                                        <option value="Thomas Cox">Thomas Cox</option>
                                                        <option value="Marcus Jones">Marcus Jones</option>
                                                        <option value="Matthew Gray">Matthew Gray</option>
                                                        <option value="Chad Davis">Chad Davis</option>
                                                        <option value="Linda Drake">Linda Drake</option>
                                                        <option value="Kathleen Flores">Kathleen Flores</option>
                                                    </select>
                                                </div>
                                                <div class="mb-5">
                                                    <label for="tag">Tag</label>
                                                    <select id="tag" class="form-select" v-model="params.tag">
                                                        <option value="">None</option>
                                                        <option value="personal">Personal</option>
                                                        <option value="work">Work</option>
                                                        <option value="social">Social</option>
                                                        <option value="important">Important</option>
                                                    </select>
                                                </div>
                                                <div class="mb-5">
                                                    <label for="desc">Description</label>
                                                    <textarea
                                                        id="desc"
                                                        rows="3"
                                                        class="form-textarea resize-none min-h-[130px]"
                                                        placeholder="Enter Description"
                                                        v-model="params.description"
                                                    ></textarea>
                                                </div>
                                                <div class="flex justify-end items-center mt-8">
                                                    <button type="button" class="btn btn-outline-danger gap-2" @click="isAddNoteModal = false">Cancel</button>
                                                    <button type="submit" class="btn btn-primary ltr:ml-4 rtl:mr-4">
                                                        {{ params.id ? 'Update Note' : 'Add Note' }}
                                                    </button>
                                                </div>
                                            </form>
                                        </div>
                                    </DialogPanel>
                                </TransitionChild>
                            </div>
                        </div>
                    </Dialog>
                </TransitionRoot>

                <TransitionRoot appear :show="isDeleteNoteModal" as="template">
                    <Dialog as="div" @close="isDeleteNoteModal = false" class="relative z-[51]">
                        <TransitionChild
                            as="template"
                            enter="duration-300 ease-out"
                            enter-from="opacity-0"
                            enter-to="opacity-100"
                            leave="duration-200 ease-in"
                            leave-from="opacity-100"
                            leave-to="opacity-0"
                        >
                            <DialogOverlay class="fixed inset-0 bg-[black]/60" />
                        </TransitionChild>

                        <div class="fixed inset-0 overflow-y-auto">
                            <div class="flex min-h-full items-center justify-center px-4 py-8">
                                <TransitionChild
                                    as="template"
                                    enter="duration-300 ease-out"
                                    enter-from="opacity-0 scale-95"
                                    enter-to="opacity-100 scale-100"
                                    leave="duration-200 ease-in"
                                    leave-from="opacity-100 scale-100"
                                    leave-to="opacity-0 scale-95"
                                >
                                    <DialogPanel class="panel border-0 p-0 rounded-lg overflow-hidden w-full max-w-lg text-black dark:text-white-dark">
                                        <button
                                            type="button"
                                            class="absolute top-4 ltr:right-4 rtl:left-4 text-gray-400 hover:text-gray-800 dark:hover:text-gray-600 outline-none"
                                            @click="isDeleteNoteModal = false"
                                        >
                                            <icon-x />
                                        </button>
                                        <div class="text-lg font-medium bg-[#fbfbfb] dark:bg-[#121c2c] ltr:pl-5 rtl:pr-5 py-3 ltr:pr-[50px] rtl:pl-[50px]">
                                            Delete Notes
                                        </div>
                                        <div class="p-5 text-center">
                                            <div class="text-white bg-danger ring-4 ring-danger/30 p-4 rounded-full w-fit mx-auto">
                                                <icon-trash-lines class="w-7 h-7 mx-auto" />
                                            </div>
                                            <div class="sm:w-3/4 mx-auto mt-5">Are you sure you want to delete Notes?</div>

                                            <div class="flex justify-center items-center mt-8">
                                                <button type="button" class="btn btn-outline-danger" @click="isDeleteNoteModal = false">Cancel</button>
                                                <button type="button" class="btn btn-primary ltr:ml-4 rtl:mr-4" @click="deleteNote">Delete</button>
                                            </div>
                                        </div>
                                    </DialogPanel>
                                </TransitionChild>
                            </div>
                        </div>
                    </Dialog>
                </TransitionRoot>

                <TransitionRoot appear :show="isViewNoteModal" as="template">
                    <Dialog as="div" @close="isViewNoteModal = false" class="relative z-[51]">
                        <TransitionChild
                            as="template"
                            enter="duration-300 ease-out"
                            enter-from="opacity-0"
                            enter-to="opacity-100"
                            leave="duration-200 ease-in"
                            leave-from="opacity-100"
                            leave-to="opacity-0"
                        >
                            <DialogOverlay class="fixed inset-0 bg-[black]/60" />
                        </TransitionChild>

                        <div class="fixed inset-0 overflow-y-auto">
                            <div class="flex min-h-full items-center justify-center px-4 py-8">
                                <TransitionChild
                                    as="template"
                                    enter="duration-300 ease-out"
                                    enter-from="opacity-0 scale-95"
                                    enter-to="opacity-100 scale-100"
                                    leave="duration-200 ease-in"
                                    leave-from="opacity-100 scale-100"
                                    leave-to="opacity-0 scale-95"
                                >
                                    <DialogPanel class="panel border-0 p-0 rounded-lg overflow-hidden w-full max-w-lg text-black dark:text-white-dark">
                                        <button
                                            type="button"
                                            class="absolute top-4 ltr:right-4 rtl:left-4 text-gray-400 hover:text-gray-800 dark:hover:text-gray-600 outline-none"
                                            @click="isViewNoteModal = false"
                                        >
                                            <icon-x />
                                        </button>
                                        <div
                                            class="flex items-center flex-wrap gap-2 text-lg font-medium bg-[#fbfbfb] dark:bg-[#121c2c] ltr:pl-5 rtl:pr-5 py-3 ltr:pr-[50px] rtl:pl-[50px]"
                                        >
                                            <div class="ltr:mr-3 rtl:ml-3">{{ selectedNote.title }}</div>
                                            <button
                                                v-show="selectedNote.tag"
                                                type="button"
                                                class="badge badge-outline-primary rounded-3xl capitalize ltr:mr-3 rtl:ml-3"
                                                :class="{
                                                    'shadow-primary': selectedNote.tag === 'personal',
                                                    'shadow-warning': selectedNote.tag === 'work',
                                                    'shadow-info': selectedNote.tag === 'social',
                                                    'shadow-danger': selectedNote.tag === 'important',
                                                }"
                                            >
                                                {{ selectedNote.tag }}
                                            </button>
                                            <button v-show="selectedNote.isFav" type="button" class="text-warning">
                                                <icon-star class="fill-warning" />
                                            </button>
                                        </div>
                                        <div class="p-5">
                                            <div class="text-base">{{ selectedNote.description }}</div>

                                            <div class="ltr:text-right rtl:text-left mt-8">
                                                <button type="button" class="btn btn-outline-danger" @click="isViewNoteModal = false">Close</button>
                                            </div>
                                        </div>
                                    </DialogPanel>
                                </TransitionChild>
                            </div>
                        </div>
                    </Dialog>
                </TransitionRoot>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import { ref, onMounted } from 'vue';
    import { TransitionRoot, TransitionChild, Dialog, DialogPanel, DialogOverlay } from '@headlessui/vue';
    import Swal from 'sweetalert2';
    import { useAppStore } from '@/stores/index';
    import { useMeta } from '@/composables/use-meta';

    import IconNotes from '@/components/icon/icon-notes.vue';
    import IconNotesEdit from '@/components/icon/icon-notes-edit.vue';
    import IconStar from '@/components/icon/icon-star.vue';
    import IconSquareRotated from '@/components/icon/icon-square-rotated.vue';
    import IconPlus from '@/components/icon/icon-plus.vue';
    import IconMenu from '@/components/icon/icon-menu.vue';
    import IconUser from '@/components/icon/icon-user.vue';
    import IconHorizontalDots from '@/components/icon/icon-horizontal-dots.vue';
    import IconPencil from '@/components/icon/icon-pencil.vue';
    import IconTrashLines from '@/components/icon/icon-trash-lines.vue';
    import IconEye from '@/components/icon/icon-eye.vue';
    import IconX from '@/components/icon/icon-x.vue';


    useMeta({ title: 'Notes' });
    const store = useAppStore();
    const defaultParams = ref({
        id: null,
        title: '',
        description: '',
        tag: '',
        user: '',
        thumb: '',
    });
    const isAddNoteModal = ref(false);
    const isDeleteNoteModal = ref(false);
    const isViewNoteModal = ref(false);
    const params = ref(JSON.parse(JSON.stringify(defaultParams.value)));
    const isShowNoteMenu = ref(false);
    const notesList = ref([
        {
            id: 1,
            user: 'Max Smith',
            thumb: 'profile-16.jpeg',
            title: 'Meeting with Kelly',
            description: 'Curabitur facilisis vel elit sed dapibus sodales purus rhoncus.',
            date: '11/01/2020',
            isFav: false,
            tag: 'personal',
        },
        {
            id: 2,
            user: 'John Doe',
            thumb: 'profile-14.jpeg',
            title: 'Receive Package',
            description: 'Facilisis curabitur facilisis vel elit sed dapibus sodales purus.',
            date: '11/02/2020',
            isFav: true,
            tag: '',
        },
        {
            id: 3,
            user: 'Kia Jain',
            thumb: 'profile-15.jpeg',
            title: 'Download Docs',
            description: 'Proin a dui malesuada, laoreet mi vel, imperdiet diam quam laoreet.',
            date: '11/04/2020',
            isFav: false,
            tag: 'work',
        },
        {
            id: 4,
            user: 'Max Smith',
            thumb: 'profile-16.jpeg',
            title: 'Meeting at 4:50pm',
            description: 'Excepteur sint occaecat cupidatat non proident, anim id est laborum.',
            date: '11/08/2020',
            isFav: false,
            tag: '',
        },
        {
            id: 5,
            user: 'Karena Courtliff',
            thumb: 'profile-17.jpeg',
            title: 'Backup Files EOD',
            description: 'Maecenas condimentum neque mollis, egestas leo ut, gravida.',
            date: '11/09/2020',
            isFav: false,
            tag: '',
        },
        {
            id: 6,
            user: 'Max Smith',
            thumb: 'profile-16.jpeg',
            title: 'Download Server Logs',
            description: 'Suspendisse efficitur diam quis gravida. Nunc molestie est eros.',
            date: '11/09/2020',
            isFav: false,
            tag: 'social',
        },
        {
            id: 7,
            user: 'Vladamir Koschek',
            thumb: '',
            title: 'Team meet at Starbucks',
            description: 'Etiam a odio eget enim aliquet laoreet lobortis sed ornare nibh.',
            date: '11/10/2020',
            isFav: false,
            tag: '',
        },
        {
            id: 8,
            user: 'Max Smith',
            thumb: 'profile-16.jpeg',
            title: 'Create new users Profile',
            description: 'Duis aute irure in nulla pariatur. Etiam a odio eget enim aliquet.',
            date: '11/11/2020',
            isFav: false,
            tag: 'important',
        },
        {
            id: 9,
            user: 'Robert Garcia',
            thumb: 'profile-21.jpeg',
            title: 'Create a compost pile',
            description: 'Zombie ipsum reversus ab viral inferno, nam rick grimes malum cerebro.',
            date: '11/12/2020',
            isFav: true,
            tag: '',
        },
        {
            id: 10,
            user: 'Marie Hamilton',
            thumb: 'profile-2.jpeg',
            title: 'Take a hike at a local park',
            description: 'De carne lumbering animata corpora quaeritis. Summus brains sit',
            date: '11/13/2020',
            isFav: true,
            tag: '',
        },
        {
            id: 11,
            user: 'Megan Meyers',
            thumb: 'profile-1.jpeg',
            title: 'Take a class at local community center that interests you',
            description: 'Cupcake ipsum dolor. Sit amet marshmallow topping cheesecake muffin.',
            date: '11/13/2020',
            isFav: false,
            tag: '',
        },
        {
            id: 12,
            user: 'Angela Hull',
            thumb: 'profile-22.jpeg',
            title: 'Research a topic interested in',
            description: 'Lemon drops tootsie roll marshmallow halvah carrot cake.',
            date: '11/14/2020',
            isFav: false,
            tag: '',
        },
        {
            id: 13,
            user: 'Karen Wolf',
            thumb: 'profile-23.jpeg',
            title: 'Plan a trip to another country',
            description: 'Space, the final frontier. These are the voyages of the Starship Enterprise.',
            date: '11/16/2020',
            isFav: true,
            tag: '',
        },
        {
            id: 14,
            user: 'Jasmine Barnes',
            thumb: 'profile-1.jpeg',
            title: 'Improve touch typing',
            description: 'Well, the way they make shows is, they make one show.',
            date: '11/16/2020',
            isFav: false,
            tag: '',
        },
        {
            id: 15,
            user: 'Thomas Cox',
            thumb: 'profile-11.jpeg',
            title: 'Learn Express.js',
            description: 'Bulbasaur Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
            date: '11/17/2020',
            isFav: false,
            tag: 'work',
        },
        {
            id: 16,
            user: 'Marcus Jones',
            thumb: 'profile-12.jpeg',
            title: 'Learn calligraphy',
            description: 'Ivysaur Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
            date: '11/17/2020',
            isFav: false,
            tag: '',
        },
        {
            id: 17,
            user: 'Matthew Gray',
            thumb: 'profile-24.jpeg',
            title: 'Have a photo session with some friends',
            description: 'Venusaur Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
            date: '11/18/2020',
            isFav: false,
            tag: 'important',
        },
        {
            id: 18,
            user: 'Chad Davis',
            thumb: 'profile-31.jpeg',
            title: 'Go to the gym',
            description: 'Charmander Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
            date: '11/18/2020',
            isFav: false,
            tag: '',
        },
        {
            id: 19,
            user: 'Linda Drake',
            thumb: 'profile-23.jpeg',
            title: 'Make own LEGO creation',
            description: 'Charmeleon Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
            date: '11/18/2020',
            isFav: false,
            tag: 'social',
        },
        {
            id: 20,
            user: 'Kathleen Flores',
            thumb: 'profile-34.jpeg',
            title: 'Take cat on a walk',
            description: 'Baseball ipsum dolor sit amet cellar rubber win hack tossed. ',
            date: '11/18/2020',
            isFav: false,
            tag: 'personal',
        },
    ]);
    const filterdNotesList: any = ref('');
    const selectedTab: any = ref('all');
    const deletedNote: any = ref(null);
    const selectedNote: any = ref({
        id: null,
        title: '',
        description: '',
        tag: '',
        user: '',
        thumb: '',
    });

    onMounted(() => {
        searchNotes();
    });

    const searchNotes = () => {
        if (selectedTab.value != 'fav') {
            if (selectedTab.value != 'all' || selectedTab.value === 'delete') {
                filterdNotesList.value = notesList.value.filter((d) => d.tag === selectedTab.value);
            } else {
                filterdNotesList.value = notesList.value;
            }
        } else {
            filterdNotesList.value = notesList.value.filter((d) => d.isFav);
        }
    };

    const saveNote = () => {
        if (!params.value.title) {
            showMessage('Title is required.', 'error');
            return false;
        }
        if (params.value.id) {
            //update task
            let note: any = notesList.value.find((d) => d.id === params.value.id);
            note.title = params.value.title;
            note.user = params.value.user;
            note.description = params.value.description;
            note.tag = params.value.tag;
        } else {
            //add note
            let maxNoteId = notesList.value.length
                ? notesList.value.reduce((max, character) => (character.id > max ? character.id : max), notesList.value[0].id)
                : 0;
            let dt = new Date();
            let note = {
                id: maxNoteId + 1,
                title: params.value.title,
                user: params.value.user,
                thumb: 'profile-21.jpeg',
                description: params.value.description,
                date: dt.getDate() + '/' + Number(dt.getMonth()) + 1 + '/' + dt.getFullYear(),
                isFav: false,
                tag: params.value.tag,
            };
            notesList.value.splice(0, 0, note);
            searchNotes();
        }

        showMessage('Note has been saved successfully.');
        isAddNoteModal.value = false;
        searchNotes();
    };

    const tabChanged = (type: string) => {
        selectedTab.value = type;
        searchNotes();
        isShowNoteMenu.value = false;
    };

    const setFav = (note: any) => {
        let item = filterdNotesList.value.find((d) => d.id === note.id);
        item.isFav = !item.isFav;
        searchNotes();
    };

    const setTag = (note: any, name: string = '') => {
        let item = filterdNotesList.value.find((d) => d.id === note.id);
        item.tag = name;
        searchNotes();
    };

    const deleteNoteConfirm = (note: any) => {
        setTimeout(() => {
            deletedNote.value = note;
            isDeleteNoteModal.value = true;
        });
    };

    const viewNote = (note: any) => {
        setTimeout(() => {
            selectedNote.value = note;
            isViewNoteModal.value = true;
        });
    };

    const editNote = (note: any = null) => {
        isShowNoteMenu.value = false;
        params.value = JSON.parse(JSON.stringify(defaultParams.value));

        if (note) {
            params.value = JSON.parse(JSON.stringify(note));
        }
        isAddNoteModal.value = true;
    };

    const deleteNote = () => {
        notesList.value = notesList.value.filter((d) => d.id != deletedNote.value.id);
        searchNotes();
        showMessage('Note has been deleted successfully.');
        isDeleteNoteModal.value = false;
    };

    const showMessage = (msg = '', type = 'success') => {
        const toast: any = Swal.mixin({
            toast: true,
            position: 'top',
            showConfirmButton: false,
            timer: 3000,
            customClass: { container: 'toast' },
        });
        toast.fire({
            icon: type,
            title: msg,
            padding: '10px 20px',
        });
    };
</script>
