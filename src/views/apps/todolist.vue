<template>
    <div>
        <div class="flex gap-5 relative sm:h-[calc(100vh_-_150px)] h-full">
            <div
                class="panel p-4 flex-none w-[240px] max-w-full absolute xl:relative z-10 space-y-4 xl:h-auto h-full xl:block ltr:xl:rounded-r-md ltr:rounded-r-none rtl:xl:rounded-l-md rtl:rounded-l-none hidden"
                :class="{ '!block': isShowTaskMenu }"
            >
                <div class="flex flex-col h-full pb-16">
                    <div class="pb-5">
                        <div class="flex text-center items-center">
                            <div class="shrink-0">
                                <icon-clipboard-text />
                            </div>
                            <h3 class="text-lg font-semibold ltr:ml-3 rtl:mr-3">Todo list</h3>
                        </div>
                    </div>
                    <div class="h-px w-full border-b border-[#e0e6ed] dark:border-[#1b2e4b] mb-5"></div>
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
                                :class="{ 'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': selectedTab === '' }"
                                @click="tabChanged('')"
                            >
                                <div class="flex items-center">
                                    <icon-list-check class="w-4.5 h-4.5 shrink-0" />
                                    <div class="ltr:ml-3 rtl:mr-3">Inbox</div>
                                </div>
                                <div class="bg-primary-light dark:bg-[#060818] rounded-md py-0.5 px-2 font-semibold whitespace-nowrap">
                                    {{ allTasks && allTasks.filter((d) => d.status != 'trash').length }}
                                </div>
                            </button>
                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{ 'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': selectedTab === 'complete' }"
                                @click="tabChanged('complete')"
                            >
                                <div class="flex items-center">
                                    <icon-thumb-up class="w-5 h-5 shrink-0" />
                                    <div class="ltr:ml-3 rtl:mr-3">Done</div>
                                </div>
                                <div class="bg-primary-light dark:bg-[#060818] rounded-md py-0.5 px-2 font-semibold whitespace-nowrap">
                                    {{ allTasks && allTasks.filter((d) => d.status === 'complete').length }}
                                </div>
                            </button>
                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{ 'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': selectedTab === 'important' }"
                                @click="tabChanged('important')"
                            >
                                <div class="flex items-center">
                                    <icon-star class="shrink-0" />

                                    <div class="ltr:ml-3 rtl:mr-3">Important</div>
                                </div>
                                <div class="bg-primary-light dark:bg-[#060818] rounded-md py-0.5 px-2 font-semibold whitespace-nowrap">
                                    {{ allTasks && allTasks.filter((d) => d.status === 'important').length }}
                                </div>
                            </button>
                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{ 'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': selectedTab === 'trash' }"
                                @click="tabChanged('trash')"
                            >
                                <div class="flex items-center">
                                    <icon-trash-lines class="shrink-0" />

                                    <div class="ltr:ml-3 rtl:mr-3">Trash</div>
                                </div>
                            </button>
                            <div class="h-px w-full border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>
                            <div class="text-white-dark px-1 py-3">Tags</div>
                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-success ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'team' }"
                                @click="tabChanged('team')"
                            >
                                <icon-square-rotated class="fill-success shrink-0" />
                                <div class="ltr:ml-3 rtl:mr-3">Team</div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-warning ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'low' }"
                                @click="tabChanged('low')"
                            >
                                <icon-square-rotated class="fill-warning shrink-0" />
                                <div class="ltr:ml-3 rtl:mr-3">Low</div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-primary ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'medium' }"
                                @click="tabChanged('medium')"
                            >
                                <icon-square-rotated class="fill-primary shrink-0" />
                                <div class="ltr:ml-3 rtl:mr-3">Medium</div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-danger ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'high' }"
                                @click="tabChanged('high')"
                            >
                                <icon-square-rotated class="fill-danger shrink-0" />
                                <div class="ltr:ml-3 rtl:mr-3">High</div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex items-center h-10 p-1 hover:bg-white-dark/10 rounded-md dark:hover:bg-[#181F32] font-medium text-info ltr:hover:pl-3 rtl:hover:pr-3 duration-300"
                                :class="{ 'ltr:pl-3 rtl:pr-3 bg-gray-100 dark:bg-[#181F32]': selectedTab === 'update' }"
                                @click="tabChanged('update')"
                            >
                                <icon-square-rotated class="fill-info shrink-0" />
                                <div class="ltr:ml-3 rtl:mr-3">Update</div>
                            </button>
                        </div>
                    </perfect-scrollbar>
                    <div class="ltr:left-0 rtl:right-0 absolute bottom-0 p-4 w-full">
                        <button class="btn btn-primary w-full" type="button" @click="addEditTask()">
                            <icon-plus class="ltr:mr-2 rtl:ml-2 shrink-0" />

                            Add New Task
                        </button>
                    </div>
                </div>
            </div>
            <div
                class="overlay bg-black/60 z-[5] w-full h-full rounded-md absolute hidden"
                :class="{ '!block xl:!hidden': isShowTaskMenu }"
                @click="isShowTaskMenu = !isShowTaskMenu"
            ></div>
            <div class="panel p-0 flex-1 overflow-auto h-full">
                <div class="flex flex-col h-full">
                    <div class="p-4 flex sm:flex-row flex-col w-full sm:items-center gap-4">
                        <div class="ltr:mr-3 rtl:ml-3 flex items-center">
                            <button type="button" class="xl:hidden hover:text-primary block ltr:mr-3 rtl:ml-3" @click="isShowTaskMenu = !isShowTaskMenu">
                                <icon-menu />
                            </button>
                            <div class="relative group flex-1">
                                <input
                                    type="text"
                                    class="form-input peer ltr:!pr-10 rtl:!pl-10"
                                    placeholder="Search Task..."
                                    v-model="searchTask"
                                    @keyup="searchTasks()"
                                />
                                <div class="absolute ltr:right-[11px] rtl:left-[11px] top-1/2 -translate-y-1/2 peer-focus:text-primary">
                                    <icon-search />
                                </div>
                            </div>
                        </div>
                        <div class="flex items-center justify-center sm:justify-end sm:flex-auto flex-1">
                            <p class="ltr:mr-3 rtl:ml-3">
                                {{ pager.startIndex + 1 + '-' + (pager.endIndex + 1) + ' of ' + filteredTasks.length }}
                            </p>
                            <button
                                type="button"
                                :disabled="pager.currentPage == 1"
                                class="bg-[#f4f4f4] rounded-md p-1 enabled:hover:bg-primary-light dark:bg-white-dark/20 enabled:dark:hover:bg-white-dark/30 ltr:mr-3 rtl:ml-3 disabled:opacity-60 disabled:cursor-not-allowed"
                                @click="pager.currentPage--, searchTasks(false)"
                            >
                                <icon-caret-down class="w-5 h-5 rtl:-rotate-90 rotate-90" />
                            </button>
                            <button
                                type="button"
                                :disabled="pager.currentPage == pager.totalPages"
                                class="bg-[#f4f4f4] rounded-md p-1 enabled:hover:bg-primary-light dark:bg-white-dark/20 enabled:dark:hover:bg-white-dark/30 disabled:opacity-60 disabled:cursor-not-allowed"
                                @click="pager.currentPage++, searchTasks(false)"
                            >
                                <icon-caret-down class="w-5 h-5 rtl:rotate-90 -rotate-90" />
                            </button>
                        </div>
                    </div>
                    <div class="h-px w-full border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>
                    <template v-if="pagedTasks.length">
                        <div class="table-responsive grow overflow-y-auto sm:min-h-[300px] min-h-[400px]">
                            <table class="table-hover">
                                <tbody>
                                    <template v-for="task in pagedTasks" :key="task.id">
                                        <tr class="group cursor-pointer" :class="{ 'bg-white-light/30 dark:bg-[#1a2941]': task.status === 'complete' }">
                                            <td class="w-1">
                                                <input
                                                    type="checkbox"
                                                    :id="`chk-${task.id}`"
                                                    class="form-checkbox"
                                                    :checked="task.status === 'complete'"
                                                    @click.stop="taskComplete(task)"
                                                    :disabled="selectedTab === 'trash'"
                                                />
                                            </td>
                                            <td>
                                                <div @click="viewTask(task)">
                                                    <div
                                                        class="group-hover:text-primary font-semibold text-base whitespace-nowrap"
                                                        :class="{ 'line-through': task.status === 'complete' }"
                                                    >
                                                        {{ task.title }}
                                                    </div>
                                                    <div
                                                        class="text-white-dark overflow-hidden min-w-[300px] line-clamp-1"
                                                        :class="{ 'line-through': task.status === 'complete' }"
                                                    >
                                                        {{ task.descriptionText }}
                                                    </div>
                                                </div>
                                            </td>
                                            <td class="w-1">
                                                <div class="flex items-center ltr:justify-end rtl:justify-start space-x-2 rtl:space-x-reverse">
                                                    <template v-if="task.priority">
                                                        <div class="dropdown">
                                                            <Popper
                                                                :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                                                offsetDistance="0"
                                                                class="align-middle"
                                                                @open:popper="isPriorityMenu = task.id"
                                                                @close:popper="isPriorityMenu = null"
                                                            >
                                                                <a
                                                                    href="javascript:;"
                                                                    class="badge rounded-full capitalize hover:top-0 hover:text-white"
                                                                    :class="{
                                                                        'badge-outline-primary hover:bg-primary': task.priority === 'medium',
                                                                        'badge-outline-warning hover:bg-warning': task.priority === 'low',
                                                                        'badge-outline-danger hover:bg-danger': task.priority === 'high',
                                                                        'text-white bg-primary': task.priority === 'medium' && isPriorityMenu === task.id,
                                                                        'text-white bg-warning': task.priority === 'low' && isPriorityMenu === task.id,
                                                                        'text-white bg-danger': task.priority === 'high' && isPriorityMenu === task.id,
                                                                    }"
                                                                >
                                                                    {{ task.priority }}
                                                                </a>
                                                                <template #content="{ close }">
                                                                    <ul @click="close()" class="text-sm text-medium">
                                                                        <li>
                                                                            <button
                                                                                type="button"
                                                                                class="w-full text-danger ltr:text-left rtl:text-right"
                                                                                @click="setPriority(task, 'high')"
                                                                            >
                                                                                High
                                                                            </button>
                                                                        </li>
                                                                        <li>
                                                                            <button
                                                                                type="button"
                                                                                class="w-full text-primary ltr:text-left rtl:text-right"
                                                                                @click="setPriority(task, 'medium')"
                                                                            >
                                                                                Medium
                                                                            </button>
                                                                        </li>
                                                                        <li>
                                                                            <button
                                                                                type="button"
                                                                                class="w-full text-warning ltr:text-left rtl:text-right"
                                                                                @click="setPriority(task, 'low')"
                                                                            >
                                                                                Low
                                                                            </button>
                                                                        </li>
                                                                    </ul>
                                                                </template>
                                                            </Popper>
                                                        </div>
                                                    </template>
                                                    <template v-if="task.tag">
                                                        <div class="dropdown">
                                                            <Popper
                                                                :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                                                offsetDistance="0"
                                                                class="align-middle"
                                                                @open:popper="isTagMenu = task.id"
                                                                @close:popper="isTagMenu = null"
                                                            >
                                                                <a
                                                                    href="javascript:;"
                                                                    class="badge rounded-full capitalize hover:top-0 hover:text-white"
                                                                    :class="{
                                                                        'badge-outline-success hover:bg-success': task.tag === 'team',
                                                                        'badge-outline-info hover:bg-info': task.tag === 'update',
                                                                        'text-white bg-success ': task.tag === 'team' && isTagMenu === task.id,
                                                                        'text-white bg-info ': task.tag === 'update' && isTagMenu === task.id,
                                                                    }"
                                                                >
                                                                    {{ task.tag }}
                                                                </a>
                                                                <template #content="{ close }">
                                                                    <ul @click="close()" class="text-sm text-medium">
                                                                        <li>
                                                                            <button type="button" class="w-full text-success" @click="setTag(task, 'team')">
                                                                                Team
                                                                            </button>
                                                                        </li>
                                                                        <li>
                                                                            <button type="button" class="w-full text-info" @click="setTag(task, 'update')">
                                                                                Update
                                                                            </button>
                                                                        </li>
                                                                        <li>
                                                                            <button type="button" class="w-full" @click="setTag(task, '')">None</button>
                                                                        </li>
                                                                    </ul>
                                                                </template>
                                                            </Popper>
                                                        </div>
                                                    </template>
                                                </div>
                                            </td>
                                            <td class="w-1">
                                                <p
                                                    class="whitespace-nowrap text-white-dark font-medium"
                                                    :class="{ 'line-through': task.status === 'complete' }"
                                                >
                                                    {{ task.date }}
                                                </p>
                                            </td>
                                            <td class="w-1">
                                                <div class="flex items-center justify-between w-max">
                                                    <div class="ltr:mr-2.5 rtl:ml-2.5 flex-shrink-0">
                                                        <div v-if="task.path">
                                                            <img :src="`/assets/images/${task.path}`" class="h-8 w-8 rounded-full object-cover" alt="avatar" />
                                                        </div>
                                                        <div
                                                            v-if="!task.path && task.assignee"
                                                            class="grid place-content-center h-8 w-8 rounded-full bg-primary text-white text-sm font-semibold"
                                                        >
                                                            {{ task.assignee.charAt(0) + '' + task.assignee.charAt(task.assignee.indexOf(' ') + 1) }}
                                                        </div>
                                                        <div
                                                            v-if="!task.path && !task.assignee"
                                                            class="border border-gray-300 dark:border-gray-800 rounded-full grid place-content-center h-8 w-8"
                                                        >
                                                            <icon-user class="w-4.5 h-4.5" />
                                                        </div>
                                                    </div>
                                                    <div class="dropdown">
                                                        <Popper
                                                            :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                                            offsetDistance="0"
                                                            class="align-middle"
                                                        >
                                                            <a href="javascript:;">
                                                                <icon-horizontal-dots class="rotate-90 opacity-70" />
                                                            </a>
                                                            <template #content="{ close }">
                                                                <ul @click="close()" class="whitespace-nowrap">
                                                                    <template v-if="selectedTab !== 'trash'">
                                                                        <li>
                                                                            <a href="javascript:;" @click="addEditTask(task)">
                                                                                <icon-pencil-paper class="w-4.5 h-4.5 ltr:mr-2 rtl:ml-2 shrink-0" />

                                                                                Edit
                                                                            </a>
                                                                        </li>
                                                                        <li>
                                                                            <a href="javascript:;" @click="deleteTask(task, 'delete')">
                                                                                <icon-trash-lines class="ltr:mr-2 rtl:ml-2 shrink-0" />
                                                                                Delete
                                                                            </a>
                                                                        </li>
                                                                        <li>
                                                                            <a href="javascript:;" @click="setImportant(task)">
                                                                                <icon-star class="w-4.5 h-4.5 ltr:mr-2 rtl:ml-2 shrink-0" />
                                                                                <span>
                                                                                    {{ task.status === 'important' ? 'Not Important' : 'Important' }}
                                                                                </span>
                                                                            </a>
                                                                        </li>
                                                                    </template>
                                                                    <template v-if="selectedTab === 'trash'">
                                                                        <li>
                                                                            <a href="javascript:;" @click="deleteTask(task, 'deletePermanent')">
                                                                                <icon-trash-lines class="ltr:mr-2 rtl:ml-2 shrink-0" />
                                                                                Permanent Delete
                                                                            </a>
                                                                        </li>
                                                                        <li>
                                                                            <a href="javascript:;" @click="deleteTask(task, 'restore')">
                                                                                <icon-restore class="ltr:mr-2 rtl:ml-2 shrink-0" />
                                                                                Restore Task
                                                                            </a>
                                                                        </li>
                                                                    </template>
                                                                </ul>
                                                            </template>
                                                        </Popper>
                                                    </div>
                                                </div>
                                            </td>
                                        </tr>
                                    </template>
                                </tbody>
                            </table>
                        </div>
                    </template>
                    <template v-if="!pagedTasks.length">
                        <div class="flex justify-center items-center sm:min-h-[300px] min-h-[400px] font-semibold text-lg h-full">No data available</div>
                    </template>
                </div>
            </div>

            <TransitionRoot appear :show="addTaskModal" as="template">
                <Dialog as="div" @close="addTaskModal = false" class="relative z-[51]">
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
                                        @click="addTaskModal = false"
                                    >
                                        <icon-x />
                                    </button>
                                    <div class="text-lg font-medium bg-[#fbfbfb] dark:bg-[#121c2c] ltr:pl-5 rtl:pr-5 py-3 ltr:pr-[50px] rtl:pl-[50px]">
                                        {{ params.id ? 'Edit Task' : 'Add Task' }}
                                    </div>
                                    <div class="p-5">
                                        <form @submit.prevent="saveTask">
                                            <div class="mb-5">
                                                <label for="title">Title</label>
                                                <input id="title" type="text" placeholder="Enter Task Title" class="form-input" v-model="params.title" />
                                            </div>
                                            <div class="mb-5">
                                                <label for="assignee">Assignee</label>
                                                <select id="assignee" class="form-select" v-model="params.assignee">
                                                    <option value="">Select Assignee</option>
                                                    <option value="John Smith">John Smith</option>
                                                    <option value="Kia Vega">Kia Vega</option>
                                                    <option value="Sandy Doe">Sandy Doe</option>
                                                    <option value="Jane Foster">Jane Foster</option>
                                                    <option value="Donna Frank">Donna Frank</option>
                                                </select>
                                            </div>
                                            <div class="mb-5 flex justify-between gap-4">
                                                <div class="flex-1">
                                                    <label for="tag">Tag</label>
                                                    <select id="tag" class="form-select" v-model="params.tag">
                                                        <option value="">Select Tag</option>
                                                        <option value="team">Team</option>
                                                        <option value="update">Update</option>
                                                    </select>
                                                </div>
                                                <div class="flex-1">
                                                    <label for="priority">Priority</label>
                                                    <select id="priority" class="form-select" v-model="params.priority">
                                                        <option value="">Select Priority</option>
                                                        <option value="low">Low</option>
                                                        <option value="medium">Medium</option>
                                                        <option value="high">High</option>
                                                    </select>
                                                </div>
                                            </div>
                                            <div class="mb-5">
                                                <label>Description</label>
                                                <quillEditor
                                                    ref="editor"
                                                    v-model:value="params.description"
                                                    :options="editorOptions"
                                                    style="min-height: 200px"
                                                    @ready="quillEditorReady($event)"
                                                ></quillEditor>
                                            </div>
                                            <div class="ltr:text-right rtl:text-left flex justify-end items-center mt-8">
                                                <button type="button" class="btn btn-outline-danger" @click="addTaskModal = false">Cancel</button>
                                                <button type="submit" class="btn btn-primary ltr:ml-4 rtl:mr-4">{{ params.id ? 'Update' : 'Add' }}</button>
                                            </div>
                                        </form>
                                    </div>
                                </DialogPanel>
                            </TransitionChild>
                        </div>
                    </div>
                </Dialog>
            </TransitionRoot>

            <TransitionRoot appear :show="viewTaskModal" as="template">
                <Dialog as="div" @close="viewTaskModal = false" class="relative z-[51]">
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
                                        @click="viewTaskModal = false"
                                    >
                                        <icon-x />
                                    </button>
                                    <div
                                        class="flex items-center flex-wrap gap-2 text-lg font-medium bg-[#fbfbfb] dark:bg-[#121c2c] ltr:pl-5 rtl:pr-5 py-3 ltr:pr-[50px] rtl:pl-[50px]"
                                    >
                                        <div>{{ selectedTask.title }}</div>
                                        <div
                                            v-show="selectedTask.priority"
                                            class="badge rounded-3xl capitalize"
                                            :class="{
                                                'badge-outline-primary': selectedTask.priority === 'medium',
                                                'badge-outline-warning ': selectedTask.priority === 'low',
                                                'badge-outline-danger ': selectedTask.priority === 'high',
                                            }"
                                        >
                                            {{ selectedTask.priority }}
                                        </div>

                                        <div
                                            v-show="selectedTask.tag"
                                            class="badge rounded-3xl capitalize"
                                            :class="{
                                                'badge-outline-success ': selectedTask.tag === 'team',
                                                'badge-outline-info ': selectedTask.tag === 'update',
                                            }"
                                        >
                                            {{ selectedTask.tag }}
                                        </div>
                                    </div>
                                    <div class="p-5">
                                        <div class="text-base prose" v-html="selectedTask.description"></div>

                                        <div class="flex justify-end items-center mt-8">
                                            <button type="button" class="btn btn-outline-danger" @click="viewTaskModal = false">Close</button>
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
</template>
<script lang="ts" setup>
    import { ref, onMounted } from 'vue';
    import { TransitionRoot, TransitionChild, Dialog, DialogPanel, DialogOverlay } from '@headlessui/vue';
    import { quillEditor } from 'vue3-quill';
    import 'vue3-quill/lib/vue3-quill.css';
    import Swal from 'sweetalert2';

    import { useAppStore } from '@/stores/index';
    import { useMeta } from '@/composables/use-meta';

    import IconClipboardText from '@/components/icon/icon-clipboard-text.vue';
    import IconListCheck from '@/components/icon/icon-list-check.vue';
    import IconThumbUp from '@/components/icon/icon-thumb-up.vue';
    import IconStar from '@/components/icon/icon-star.vue';
    import IconTrashLines from '@/components/icon/icon-trash-lines.vue';
    import IconSquareRotated from '@/components/icon/icon-square-rotated.vue';
    import IconPlus from '@/components/icon/icon-plus.vue';
    import IconMenu from '@/components/icon/icon-menu.vue';
    import IconSearch from '@/components/icon/icon-search.vue';
    import IconCaretDown from '@/components/icon/icon-caret-down.vue';
    import IconUser from '@/components/icon/icon-user.vue';
    import IconHorizontalDots from '@/components/icon/icon-horizontal-dots.vue';
    import IconPencilPaper from '@/components/icon/icon-pencil-paper.vue';
    import IconRestore from '@/components/icon/icon-restore.vue';
    import IconX from '@/components/icon/icon-x.vue';

    useMeta({ title: 'Todolist' });
    const store = useAppStore();

    const defaultParams = ref({
        id: null,
        title: '',
        description: '',
        descriptionText: '',
        assignee: '',
        path: '',
        tag: '',
        priority: 'low',
    });

    const selectedTab = ref('');
    const isShowTaskMenu = ref(false);
    const addTaskModal = ref(false);
    const viewTaskModal = ref(false);

    const params = ref(JSON.parse(JSON.stringify(defaultParams.value)));
    const allTasks = ref([
        {
            id: 1,
            title: 'Meeting with Shaun Park at 4:50pm',
            date: 'Aug, 07 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'team',
            priority: 'medium',
            assignee: 'John Smith',
            path: '',
            status: '',
        },
        {
            id: 2,
            title: 'Team meet at Starbucks',
            date: 'Aug, 06 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'team',
            priority: 'low',
            assignee: 'John Smith',
            path: 'profile-15.jpeg',
            status: '',
        },
        {
            id: 3,
            title: 'Meet Lisa to discuss project details',
            date: 'Aug, 05 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'update',
            priority: 'medium',
            assignee: 'John Smith',
            path: 'profile-1.jpeg',
            status: 'complete',
        },
        {
            id: 4,
            title: 'Download Complete',
            date: 'Aug, 04 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: 'low',
            assignee: 'John Smith',
            path: 'profile-16.jpeg',
            status: '',
        },
        {
            id: 5,
            title: 'Conference call with Marketing Manager',
            date: 'Aug, 03 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'update',
            priority: 'high',
            assignee: 'John Smith',
            path: 'profile-5.jpeg',
            status: 'important',
        },
        {
            id: 6,
            title: 'New User Registered',
            date: 'Aug, 02 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: 'medium',
            assignee: '',
            path: '',
            status: 'important',
        },
        {
            id: 7,
            title: 'Fix issues in new project',
            date: 'Aug, 01 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'team',
            priority: 'medium',
            assignee: 'John Smith',
            path: 'profile-17.jpeg',
            status: '',
        },
        {
            id: 8,
            title: 'Check All functionality',
            date: 'Aug, 07 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'update',
            priority: 'medium',
            assignee: 'John Smith',
            path: 'profile-18.jpeg',
            status: 'important',
        },
        {
            id: 9,
            title: 'Check Repository',
            date: 'Aug, 07 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'team',
            priority: 'medium',
            assignee: 'John Smith',
            path: 'profile-20.jpeg',
            status: 'complete',
        },
        {
            id: 10,
            title: 'Trashed Tasks',
            date: 'Aug, 08 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'team',
            priority: 'medium',
            assignee: 'John Smith',
            path: 'profile-15.jpeg',
            status: 'trash',
        },
        {
            id: 11,
            title: 'Trashed Tasks 2',
            date: 'Aug, 09 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: 'medium',
            assignee: 'John Smith',
            path: 'profile-2.jpeg',
            status: 'trash',
        },
        {
            id: 12,
            title: 'Trashed Tasks 3',
            date: 'Aug, 10 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: 'team',
            priority: 'medium',
            assignee: 'John Smith',
            path: 'profile-24.jpeg',
            status: 'trash',
        },
        {
            id: 13,
            title: 'Do something nice for someone I care about',
            date: 'Sep, 10 2022',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-25.jpeg',
            status: '',
        },
        {
            id: 14,
            title: 'Memorize the fifty states and their capitals',
            date: 'Sep, 13 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-11.jpeg',
            status: '',
        },
        {
            id: 15,
            title: 'Watch a classic movie',
            date: 'Oct, 10 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-10.jpeg',
            status: '',
        },
        {
            id: 16,
            title: 'Contribute code or a monetary donation to an open-source software project',
            date: 'Nov, 10 2017',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-12.jpeg',
            status: '',
        },
        {
            id: 17,
            title: 'Solve a Rubik`s cube',
            date: 'Nov, 15 2017',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-25.jpeg',
            status: '',
        },
        {
            id: 18,
            title: 'Bake pastries for me and neighbor',
            date: 'Mar, 19 2018',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-27.jpeg',
            status: '',
        },
        {
            id: 19,
            title: 'Go see a Broadway production',
            date: 'Oct, 2 2018',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-26.jpeg',
            status: '',
        },
        {
            id: 20,
            title: 'Write a thank you letter to an influential person in my life',
            date: 'Nov, 20 2018',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-18.jpeg',
            status: '',
        },
        {
            id: 21,
            title: 'Invite some friends over for a game night',
            date: 'Jun 6 2019',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-13.jpeg',
            status: '',
        },
        {
            id: 22,
            title: 'Have a football scrimmage with some friends',
            date: 'Sep, 13 2019',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-24.jpeg',
            status: '',
        },
        {
            id: 23,
            title: 'Text a friend I haven`t talked to in a long time',
            date: 'Oct, 10 2019',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-20.jpeg',
            status: '',
        },
        {
            id: 24,
            title: 'Organize pantry',
            date: 'Feb, 24 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-10.jpeg',
            status: '',
        },
        {
            id: 25,
            title: 'Buy a new house decoration',
            date: 'Mar, 25 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-9.jpeg',
            status: '',
        },
        {
            id: 26,
            title: 'Plan a vacation I`ve always wanted to take',
            date: 'Mar, 30 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-4.jpeg',
            status: '',
        },
        {
            id: 27,
            title: 'Clean out car',
            date: 'Apr, 3 2020',
            description:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            descriptionText:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.',
            tag: '',
            priority: '',
            assignee: 'John Smith',
            path: 'profile-3.jpeg',
            status: '',
        },
    ]);
    const filteredTasks: any = ref([]);
    const pagedTasks: any = ref([]);
    const searchTask = ref('');
    const selectedTask: any = ref(defaultParams.value);
    const isPriorityMenu: any = ref(null);
    const isTagMenu: any = ref(null);

    const pager = ref({
        currentPage: 1,
        totalPages: 0,
        pageSize: 10,
        startIndex: 0,
        endIndex: 0,
    });

    const editorOptions = ref({
        modules: {
            toolbar: [[{ header: [1, 2, false] }], ['bold', 'italic', 'underline', 'link'], [{ list: 'ordered' }, { list: 'bullet' }], ['clean']],
        },
        placeholder: '',
    });
    const quillEditorObj: any = ref(null);

    onMounted(() => {
        searchTasks();
    });

    const quillEditorReady = (quill: any) => {
        quillEditorObj.value = quill;
    };

    const searchTasks = (isResetPage = true) => {
        if (isResetPage) {
            pager.value.currentPage = 1;
        }
        let res;
        if (selectedTab.value === 'complete' || selectedTab.value === 'important' || selectedTab.value === 'trash') {
            res = allTasks.value.filter((d) => d.status === selectedTab.value);
        } else {
            res = allTasks.value.filter((d) => d.status != 'trash');
        }

        if (selectedTab.value === 'team' || selectedTab.value === 'update') {
            res = res.filter((d) => d.tag === selectedTab.value);
        } else if (selectedTab.value === 'high' || selectedTab.value === 'medium' || selectedTab.value === 'low') {
            res = res.filter((d) => d.priority === selectedTab.value);
        }
        filteredTasks.value = res.filter((d) => d.title?.toLowerCase().includes(searchTask.value));
        getPager();
    };

    const getPager = () => {
        setTimeout(() => {
            if (filteredTasks.value.length) {
                pager.value.totalPages = pager.value.pageSize < 1 ? 1 : Math.ceil(filteredTasks.value.length / pager.value.pageSize);
                if (pager.value.currentPage > pager.value.totalPages) {
                    pager.value.currentPage = 1;
                }
                pager.value.startIndex = (pager.value.currentPage - 1) * pager.value.pageSize;
                pager.value.endIndex = Math.min(pager.value.startIndex + pager.value.pageSize - 1, filteredTasks.value.length - 1);
                pagedTasks.value = filteredTasks.value.slice(pager.value.startIndex, pager.value.endIndex + 1);
            } else {
                pagedTasks.value = [];
                pager.value.startIndex = -1;
                pager.value.endIndex = -1;
            }
        });
    };

    const setPriority = (task: any, name: string = '') => {
        let item = filteredTasks.value.find((d) => d.id === task.id);
        item.priority = name;
        searchTasks(false);
    };

    const setTag = (task: any, name: string = '') => {
        let item = filteredTasks.value.find((d) => d.id === task.id);
        item.tag = name;
        searchTasks(false);
    };

    const tabChanged = (type: any = null) => {
        selectedTab.value = type;
        searchTasks();
        isShowTaskMenu.value = false;
    };

    const taskComplete = (task: any = null) => {
        let item = filteredTasks.value.find((d) => d.id === task.id);
        item.status = item.status === 'complete' ? '' : 'complete';
        searchTasks(false);
    };

    const setImportant = (task: any = null) => {
        let item = filteredTasks.value.find((d) => d.id === task.id);
        item.status = item.status === 'important' ? '' : 'important';
        searchTasks(false);
    };

    const viewTask = (item: any = null) => {
        selectedTask.value = item;
        setTimeout(() => {
            viewTaskModal.value = true;
        });
    };

    const addEditTask = (task: any = null) => {
        isShowTaskMenu.value = false;

        params.value = JSON.parse(JSON.stringify(defaultParams.value));

        if (task) {
            params.value = JSON.parse(JSON.stringify(task));
        }

        addTaskModal.value = true;
    };

    const deleteTask = (task: any, type: string = '') => {
        if (type === 'delete') {
            task.status = 'trash';
        }
        if (type === 'deletePermanent') {
            allTasks.value = allTasks.value.filter((d: any) => d.id != task.id);
        } else if (type === 'restore') {
            task.status = '';
        }
        searchTasks(false);
    };

    const saveTask = () => {
        if (!params.value.title) {
            showMessage('Title is required.', 'error');
            return false;
        }

        if (params.value.id) {
            //update task
            pagedTasks.value = pagedTasks.value.map((d: any) => {
                if (d.id === params.value.id) {
                    d = params.value;
                    d.descriptionText = quillEditorObj.value.getText();
                }
                return d;
            });
        } else {
            //add task
            const maxid = allTasks.value.length ? allTasks.value.reduce((max, obj) => (obj.id > max ? obj.id : max), allTasks.value[0].id) : 0;

            const today = new Date();
            const dd = String(today.getDate()).padStart(2, '0');
            const mm = String(today.getMonth());
            const yyyy = today.getFullYear();
            const monthNames: any = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];

            let task = params.value;
            task.id = maxid + 1;
            task.descriptionText = quillEditorObj.value.getText();
            task.date = monthNames[mm] + ', ' + dd + ' ' + yyyy;

            allTasks.value.splice(0, 0, task);
            searchTasks();
        }

        showMessage('Task has been saved successfully.');
        addTaskModal.value = false;
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
