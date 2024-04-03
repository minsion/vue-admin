<template>
    <div>
        <div class="flex gap-5 relative sm:h-[calc(100vh_-_150px)] h-full">
            <div
                class="overlay bg-black/60 z-[5] w-full h-full absolute rounded-md hidden"
                :class="{ '!block xl:!hidden': isShowMailMenu }"
                @click="isShowMailMenu = !isShowMailMenu"
            ></div>
            <div
                class="panel xl:block p-4 dark:gray-50 w-[250px] max-w-full flex-none space-y-3 xl:relative absolute z-10 xl:h-auto h-full hidden ltr:xl:rounded-r-md ltr:rounded-r-none rtl:xl:rounded-l-md rtl:rounded-l-none overflow-hidden"
                :class="{ '!block': isShowMailMenu }"
            >
                <div class="flex flex-col h-full pb-16">
                    <div class="pb-5">
                        <button class="btn btn-primary w-full" type="button" @click="openMail('add', null)">New Message</button>
                    </div>
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
                                :class="{
                                    'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': !isEdit && selectedTab === 'inbox',
                                }"
                                @click="tabChanged('inbox')"
                            >
                                <div class="flex items-center">
                                    <icon-mail class="w-5 h-5 shrink-0" />

                                    <div class="ltr:ml-3 rtl:mr-3">Inbox</div>
                                </div>
                                <div class="bg-primary-light dark:bg-[#060818] rounded-md py-0.5 px-2 font-semibold whitespace-nowrap">
                                    {{ mailList && mailList.filter((d) => d.type == 'inbox').length }}
                                </div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{
                                    'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': !isEdit && selectedTab === 'star',
                                }"
                                @click="tabChanged('star')"
                            >
                                <div class="flex items-center">
                                    <icon-star class="shrink-0" />
                                    <div class="ltr:ml-3 rtl:mr-3">Marked</div>
                                </div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{
                                    'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': !isEdit && selectedTab === 'sent_mail',
                                }"
                                @click="tabChanged('sent_mail')"
                            >
                                <div class="flex items-center">
                                    <icon-send class="shrink-0" />

                                    <div class="ltr:ml-3 rtl:mr-3">Sent</div>
                                </div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{
                                    'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': !isEdit && selectedTab === 'spam',
                                }"
                                @click="tabChanged('spam')"
                            >
                                <div class="flex items-center">
                                    <icon-info-hexagon class="shrink-0" />

                                    <div class="ltr:ml-3 rtl:mr-3">Spam</div>
                                </div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{
                                    'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': !isEdit && selectedTab === 'draft',
                                }"
                                @click="tabChanged('draft')"
                            >
                                <div class="flex items-center">
                                    <icon-file class="w-4.5 h-4.5" />
                                    <div class="ltr:ml-3 rtl:mr-3">Drafts</div>
                                </div>
                                <div class="bg-primary-light dark:bg-[#060818] rounded-md py-0.5 px-2 font-semibold whitespace-nowrap">
                                    {{ mailList && mailList.filter((d) => !d.type || d.type === 'draft').length }}
                                </div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                :class="{
                                    'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': !isEdit && selectedTab === 'trash',
                                }"
                                @click="tabChanged('trash')"
                            >
                                <div class="flex items-center">
                                    <icon-trash-lines class="shrink-0" />

                                    <div class="ltr:ml-3 rtl:mr-3">Trash</div>
                                </div>
                            </button>

                            <disclosure as="div" v-slot="{ open }">
                                <disclosure-button
                                    class="w-full flex items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                >
                                    <icon-caret-down class="w-5 h-5 shrink-0" :class="{ 'rotate-180': open }" />
                                    <div class="ltr:ml-3 rtl:mr-3">{{ open ? 'Less' : 'More' }}</div>
                                </disclosure-button>

                                <transition>
                                    <disclosure-panel as="ul" :unmount="false" class="mt-1 space-y-1">
                                        <li>
                                            <button
                                                type="button"
                                                class="w-full flex items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                                :class="{
                                                    'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': !isEdit && selectedTab === 'archive',
                                                }"
                                                @click="tabChanged('archive')"
                                            >
                                                <icon-archive class="shrink-0" />

                                                <div class="ltr:ml-3 rtl:mr-3">Archive</div>
                                            </button>
                                        </li>
                                        <li>
                                            <button
                                                type="button"
                                                class="w-full flex items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                                                :class="{
                                                    'bg-gray-100 dark:text-primary text-primary dark:bg-[#181F32]': !isEdit && selectedTab === 'important',
                                                }"
                                                @click="tabChanged('important')"
                                            >
                                                <icon-bookmark class="shrink-0" />

                                                <div class="ltr:ml-3 rtl:mr-3">Important</div>
                                            </button>
                                        </li>
                                    </disclosure-panel>
                                </transition>
                            </disclosure>

                            <div class="h-px border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>

                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                            >
                                <div class="flex items-center">
                                    <icon-video class="shrink-0" />

                                    <div class="ltr:ml-3 rtl:mr-3">New meeting</div>
                                </div>
                            </button>

                            <button
                                type="button"
                                class="w-full flex justify-between items-center p-2 hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium h-10"
                            >
                                <div class="flex items-center">
                                    <icon-chart-square class="shrink-0 rotate-180" />
                                    <div class="ltr:ml-3 rtl:mr-3">Join a meeting</div>
                                </div>
                            </button>
                            <div class="h-px border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>
                        </div>
                    </perfect-scrollbar>
                    <div class="ltr:left-0 rtl:right-0 absolute bottom-0 p-4 w-full">
                        <button
                            type="button"
                            class="w-full flex p-2 justify-between items-center hover:bg-white-dark/10 rounded-md dark:hover:text-primary hover:text-primary dark:hover:bg-[#181F32] font-medium group"
                            @click="isShowMailMenu = false"
                        >
                            <div class="flex items-center">
                                <icon-user-plus class="shrink-0" />

                                <div class="ltr:ml-3 rtl:mr-3">Add Account</div>
                            </div>
                            <div class="bg-primary-light dark:bg-[#060818] rounded-md py-1 px-2">
                                <icon-plus />
                            </div>
                        </button>
                    </div>
                </div>
            </div>
            <div class="panel p-0 flex-1 overflow-x-hidden h-full">
                <div v-show="!selectedMail && !isEdit" class="flex flex-col h-full">
                    <div class="flex justify-between items-center flex-wrap-reverse gap-4 p-4">
                        <div class="flex items-center w-full sm:w-auto">
                            <div class="ltr:mr-4 rtl:ml-4">
                                <input
                                    type="checkbox"
                                    class="form-checkbox"
                                    :checked="checkAllCheckbox"
                                    :value="checkAllCheckbox"
                                    @change="checkAll($event.target.checked)"
                                />
                            </div>
                            <div class="ltr:mr-4 rtl:ml-4">
                                <button type="button" v-tippy:refresh class="hover:text-primary flex items-center" @click="refreshMails()">
                                    <icon-refresh />
                                </button>
                                <tippy target="refresh">Refresh</tippy>
                            </div>
                            <template v-if="selectedTab != 'trash'">
                                <ul class="flex grow items-center sm:flex-none gap-4 ltr:sm:mr-4 rtl:sm:ml-4">
                                    <li>
                                        <div>
                                            <button type="button" v-tippy:archive class="hover:text-primary flex items-center" @click="setArchive">
                                                <icon-archive />
                                            </button>
                                            <tippy target="archive">Archive</tippy>
                                        </div>
                                    </li>
                                    <li>
                                        <div @click="setSpam">
                                            <button type="button" v-tippy:spam class="hover:text-primary flex items-center">
                                                <icon-info-hexagon />
                                            </button>
                                            <tippy target="spam">Spam</tippy>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="dropdown">
                                            <Popper
                                                :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                                offsetDistance="0"
                                                class="align-middle"
                                            >
                                                <div>
                                                    <button type="button" v-tippy:group class="hover:text-primary flex items-center">
                                                        <icon-wheel />
                                                    </button>
                                                    <tippy target="group">Group</tippy>
                                                </div>
                                                <template #content="{ close }">
                                                    <ul @click="close()">
                                                        <li>
                                                            <a href="javascript:;" @click="setGroup('personal')">
                                                                <div class="w-2 h-2 rounded-full bg-primary ltr:mr-3 rtl:ml-3 shrink-0"></div>
                                                                Personal
                                                            </a>
                                                        </li>
                                                        <li>
                                                            <a href="javascript:;" @click="setGroup('work')">
                                                                <div class="w-2 h-2 rounded-full bg-warning ltr:mr-3 rtl:ml-3 shrink-0"></div>
                                                                Work
                                                            </a>
                                                        </li>
                                                        <li>
                                                            <a href="javascript:;" @click="setGroup('social')">
                                                                <div class="w-2 h-2 rounded-full bg-success ltr:mr-3 rtl:ml-3 shrink-0"></div>
                                                                Social
                                                            </a>
                                                        </li>
                                                        <li>
                                                            <a href="javascript:;" @click="setGroup('private')">
                                                                <div class="w-2 h-2 rounded-full bg-danger ltr:mr-3 rtl:ml-3 shrink-0"></div>
                                                                Private
                                                            </a>
                                                        </li>
                                                    </ul>
                                                </template>
                                            </Popper>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="dropdown">
                                            <Popper
                                                :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                                offsetDistance="0"
                                                class="align-middle"
                                            >
                                                <button type="button" class="hover:text-primary flex items-center">
                                                    <icon-horizontal-dots class="rotate-90 opacity-70" />
                                                </button>
                                                <template #content="{ close }">
                                                    <ul @click="close()" class="whitespace-nowrap">
                                                        <li>
                                                            <a href="javascript:;" class="w-full" @click="setAction('read')">
                                                                <icon-open-book class="ltr:mr-2 rtl:ml-2 shrink-0" />

                                                                Mark as Read
                                                            </a>
                                                        </li>
                                                        <li>
                                                            <a href="javascript:;" class="w-full" @click="setAction('unread')">
                                                                <icon-book class="ltr:mr-2 rtl:ml-2 shrink-0" />

                                                                Mark as Unread
                                                            </a>
                                                        </li>
                                                        <li>
                                                            <a href="javascript:;" class="w-full" @click="setAction('trash')">
                                                                <icon-trash-lines class="ltr:mr-2 rtl:ml-2 shrink-0" />

                                                                Trash
                                                            </a>
                                                        </li>
                                                    </ul>
                                                </template>
                                            </Popper>
                                        </div>
                                    </li>
                                </ul>
                            </template>
                            <template v-if="selectedTab == 'trash'">
                                <ul class="flex flex-1 items-center sm:flex-none gap-4 ltr:sm:mr-3 rtl:sm:ml-4">
                                    <li>
                                        <div>
                                            <button type="button" v-tippy:delete class="block hover:text-primary" @click="setAction('delete')">
                                                <icon-trash />
                                            </button>
                                            <tippy target="delete">Permanently Delete</tippy>
                                        </div>
                                    </li>
                                    <li>
                                        <div>
                                            <button type="button" v-tippy:restore class="block hover:text-primary" @click="setAction('restore')">
                                                <icon-restore />
                                            </button>
                                            <tippy target="restore">Restore</tippy>
                                        </div>
                                    </li>
                                </ul>
                            </template>
                        </div>
                        <div class="flex justify-between items-center sm:w-auto w-full">
                            <div class="flex items-center ltr:mr-4 rtl:ml-4">
                                <button type="button" class="xl:hidden hover:text-primary block ltr:mr-3 rtl:ml-3" @click="isShowMailMenu = !isShowMailMenu">
                                    <icon-menu />
                                </button>
                                <div class="relative group">
                                    <input
                                        type="text"
                                        placeholder="Search Mail"
                                        class="form-input ltr:pr-8 rtl:pl-8 peer"
                                        v-model="searchText"
                                        @keyup="searchMails()"
                                    />
                                    <div class="absolute ltr:right-[11px] rtl:left-[11px] top-1/2 -translate-y-1/2 peer-focus:text-primary">
                                        <icon-search />
                                    </div>
                                </div>
                            </div>
                            <div class="flex items-center">
                                <div class="ltr:mr-4 rtl:ml-4">
                                    <button type="button" v-tippy:settings class="hover:text-primary">
                                        <icon-settings />
                                    </button>
                                    <tippy target="settings">Settings</tippy>
                                </div>
                                <div>
                                    <button type="button" v-tippy:help class="hover:text-primary">
                                        <icon-help-circle class="w-6 h-6" />
                                    </button>
                                    <tippy target="help">Help</tippy>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="h-px border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>
                    <div class="flex flex-wrap flex-col md:flex-row xl:w-auto justify-between items-center px-4 pb-4">
                        <div class="w-full sm:w-auto grid grid-cols-2 sm:grid-cols-4 gap-3 mt-4">
                            <button
                                type="button"
                                class="btn btn-outline-primary flex"
                                :class="{ 'text-white bg-primary': selectedTab === 'personal' }"
                                @click="tabChanged('personal')"
                            >
                                <icon-user class="w-5 h-5 ltr:mr-2 rtl:ml-2" />

                                Personal
                            </button>

                            <button
                                type="button"
                                class="btn btn-outline-warning flex"
                                :class="{ 'text-white bg-warning': selectedTab === 'work' }"
                                @click="tabChanged('work')"
                            >
                                <icon-message-2 class="w-5 h-5 ltr:mr-2 rtl:ml-2" />

                                Work
                            </button>

                            <button
                                type="button"
                                class="btn btn-outline-success flex"
                                :class="{ 'text-white bg-success': selectedTab === 'social' }"
                                @click="tabChanged('social')"
                            >
                                <icon-users class="ltr:mr-2 rtl:ml-2" />

                                Social
                            </button>

                            <button
                                type="button"
                                class="btn btn-outline-danger flex"
                                :class="{ 'text-white bg-danger': selectedTab === 'private' }"
                                @click="tabChanged('private')"
                            >
                                <icon-tag class="ltr:mr-2 rtl:ml-2" />

                                Private
                            </button>
                        </div>
                        <div class="mt-4 md:flex-auto flex-1">
                            <div class="flex items-center md:justify-end justify-center">
                                <div class="ltr:mr-3 rtl:ml-3">
                                    {{ pager.startIndex + 1 + '-' + (pager.endIndex + 1) + ' of ' + filteredMailList.length }}
                                </div>
                                <button
                                    type="button"
                                    :disabled="pager.currentPage == 1"
                                    class="bg-[#f4f4f4] rounded-md p-1 enabled:hover:bg-primary-light dark:bg-white-dark/20 enabled:dark:hover:bg-white-dark/30 ltr:mr-3 rtl:ml-3 disabled:opacity-60 disabled:cursor-not-allowed"
                                    @click="pager.currentPage--, searchMails(false)"
                                >
                                    <icon-caret-down class="w-5 h-5 rtl:-rotate-90 rotate-90" />
                                </button>
                                <button
                                    type="button"
                                    :disabled="pager.currentPage == pager.totalPages"
                                    class="bg-[#f4f4f4] rounded-md p-1 enabled:hover:bg-primary-light dark:bg-white-dark/20 enabled:dark:hover:bg-white-dark/30 disabled:opacity-60 disabled:cursor-not-allowed"
                                    @click="pager.currentPage++, searchMails(false)"
                                >
                                    <icon-caret-down class="w-5 h-5 rtl:rotate-90 -rotate-90" />
                                </button>
                            </div>
                        </div>
                    </div>
                    <div class="h-px border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>
                    <template v-if="pagedMails.length">
                        <div class="table-responsive grow overflow-y-auto min-h-[300px]">
                            <table>
                                <tbody>
                                    <template v-for="mail in pagedMails" :key="mail.id">
                                        <tr class="cursor-pointer" @click="selectMail(mail)">
                                            <td>
                                                <div class="flex items-center whitespace-nowrap">
                                                    <div class="ltr:mr-3 rtl:ml-3">
                                                        <input
                                                            type="checkbox"
                                                            :id="`chk-${mail.id}`"
                                                            v-model.number="ids"
                                                            :value="mail.id"
                                                            @click="$event.stopPropagation()"
                                                            class="form-checkbox"
                                                        />
                                                    </div>
                                                    <div class="ltr:mr-3 rtl:ml-3">
                                                        <button
                                                            type="button"
                                                            v-tippy:star
                                                            class="enabled:hover:text-warning disabled:opacity-60 flex items-center"
                                                            :class="{ 'text-warning': mail.isStar }"
                                                            @click.stop="setStar(mail.id)"
                                                            :disabled="selectedTab === 'trash'"
                                                        >
                                                            <icon-star :class="{ 'fill-warning': mail.isStar }" />
                                                        </button>
                                                        <tippy target="star">Star</tippy>
                                                    </div>
                                                    <div class="ltr:mr-3 rtl:ml-3">
                                                        <button
                                                            type="button"
                                                            v-tippy:important
                                                            class="enabled:hover:text-primary disabled:opacity-60 rotate-90 flex items-center"
                                                            :class="{ 'text-primary': mail.isImportant }"
                                                            @click.stop="setImportant(mail.id)"
                                                            :disabled="selectedTab === 'trash'"
                                                        >
                                                            <icon-bookmark
                                                                :bookmark="false"
                                                                class="w-4.5 h-4.5"
                                                                :class="{ 'fill-primary': mail.isImportant }"
                                                            />
                                                        </button>
                                                        <tippy target="important">Important</tippy>
                                                    </div>
                                                    <div
                                                        class="dark:text-gray-300 whitespace-nowrap font-semibold"
                                                        :class="{
                                                            'text-gray-500 dark:!text-gray-500 font-normal': !mail.isUnread,
                                                        }"
                                                    >
                                                        {{ mail.firstName ? mail.firstName + ' ' + mail.lastName : mail.email }}
                                                    </div>
                                                </div>
                                            </td>
                                            <td>
                                                <div class="font-medium text-white-dark overflow-hidden min-w-[300px] line-clamp-1">
                                                    <span
                                                        :class="{
                                                            'text-gray-800 dark:text-gray-300 font-semibold': mail.isUnread,
                                                        }"
                                                    >
                                                        <span>{{ mail.title }}</span> &minus; <span>{{ mail.displayDescription }}</span></span
                                                    >
                                                </div>
                                            </td>
                                            <td>
                                                <div class="flex items-center">
                                                    <div
                                                        class="w-2 h-2 rounded-full"
                                                        :class="{
                                                            'bg-primary': mail.group === 'personal',
                                                            'bg-warning': mail.group === 'work',
                                                            'bg-success': mail.group === 'social',
                                                            'bg-danger': mail.group === 'private',
                                                        }"
                                                    ></div>
                                                    <template v-if="mail.attachments">
                                                        <div class="ltr:ml-4 rtl:mr-4">
                                                            <icon-paperclip />
                                                        </div>
                                                    </template>
                                                </div>
                                            </td>
                                            <td class="whitespace-nowrap font-medium ltr:text-right rtl:text-left">
                                                {{ showTime(mail) }}
                                            </td>
                                        </tr>
                                    </template>
                                </tbody>
                            </table>
                        </div>
                    </template>
                    <template v-if="!pagedMails.length">
                        <div class="grid place-content-center min-h-[300px] font-semibold text-lg h-full">No data available</div>
                    </template>
                </div>
                <template v-if="selectedMail && !isEdit">
                    <div>
                        <div class="flex items-center justify-between flex-wrap p-4">
                            <div class="flex items-center">
                                <button type="button" class="ltr:mr-2 rtl:ml-2 hover:text-primary" @click="selectedMail = null">
                                    <icon-arrow-left class="w-5 h-5 rotate-180" />
                                </button>
                                <h4 class="text-base md:text-lg font-medium ltr:mr-2 rtl:ml-2">
                                    {{ selectedMail.title }}
                                </h4>
                                <div class="badge bg-info hover:top-0">{{ selectedMail.type }}</div>
                            </div>
                            <div>
                                <button type="button" v-tippy:print>
                                    <icon-printer />
                                </button>
                                <tippy target="print">Print</tippy>
                            </div>
                        </div>
                        <div class="h-px border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>
                        <div class="p-4 relative">
                            <div class="flex flex-wrap">
                                <div class="flex-shrink-0 ltr:mr-2 rtl:ml-2">
                                    <img
                                        v-show="selectedMail.path"
                                        :src="`/assets/images/${selectedMail.path}`"
                                        class="h-12 w-12 rounded-full object-cover"
                                        alt="avatar"
                                    />
                                    <div v-show="!selectedMail.path" class="border border-gray-300 dark:border-gray-800 rounded-full p-3">
                                        <icon-user class="w-5 h-5" />
                                    </div>
                                </div>
                                <div class="ltr:mr-2 rtl:ml-2 flex-1">
                                    <div class="flex items-center">
                                        <div class="text-lg ltr:mr-4 rtl:ml-4 whitespace-nowrap">
                                            {{ selectedMail.firstName ? selectedMail.firstName + ' ' + selectedMail.lastName : selectedMail.email }}
                                        </div>
                                        <div>
                                            <div v-show="selectedMail.group" class="ltr:mr-4 rtl:ml-4">
                                                <div
                                                    v-tippy:group
                                                    class="w-2 h-2 rounded-full"
                                                    :class="{
                                                        'bg-primary': selectedMail.group === 'personal',
                                                        'bg-warning': selectedMail.group === 'work',
                                                        'bg-success': selectedMail.group === 'social',
                                                        'bg-danger': selectedMail.group === 'private',
                                                    }"
                                                ></div>
                                                <tippy target="group" class="capitalize">{{ selectedMail.group }}</tippy>
                                            </div>
                                        </div>
                                        <div class="text-white-dark whitespace-nowrap">1 days ago</div>
                                    </div>
                                    <div class="text-white-dark flex items-center">
                                        <div class="ltr:mr-1 rtl:ml-1">
                                            {{ selectedMail.type === 'sent_mail' ? selectedMail.email : 'to me' }}
                                        </div>
                                        <div class="dropdown">
                                            <Popper
                                                :placement="store.rtlClass === 'rtl' ? 'bottom-start' : 'bottom-end'"
                                                offsetDistance="0"
                                                class="align-middle"
                                            >
                                                <button type="button" class="mt-1.5">
                                                    <icon-caret-down class="w-5 h-5" />
                                                </button>
                                                <template #content>
                                                    <ul class="sm:w-56">
                                                        <li>
                                                            <div class="flex items-center px-4 py-2">
                                                                <div class="text-white-dark ltr:mr-2 rtl:ml-2 w-1/4">From:</div>
                                                                <div class="flex-1">
                                                                    {{ selectedMail.type === 'sent_mail' ? 'tailly@gmail.com' : selectedMail.email }}
                                                                </div>
                                                            </div>
                                                        </li>
                                                        <li>
                                                            <div class="flex items-center px-4 py-2">
                                                                <div class="text-white-dark ltr:mr-2 rtl:ml-2 w-1/4">To:</div>
                                                                <div class="flex-1">
                                                                    {{ selectedMail.type !== 'sent_mail' ? 'tailly@gmail.com' : selectedMail.email }}
                                                                </div>
                                                            </div>
                                                        </li>
                                                        <li>
                                                            <div class="flex items-center px-4 py-2">
                                                                <div class="text-white-dark ltr:mr-2 rtl:ml-2 w-1/4">Date:</div>
                                                                <div class="flex-1">
                                                                    {{ selectedMail.date + ', ' + selectedMail.time }}
                                                                </div>
                                                            </div>
                                                        </li>
                                                        <li>
                                                            <div class="flex items-center px-4 py-2">
                                                                <div class="text-white-dark ltr:mr-2 rtl:ml-2 w-1/4">Subject:</div>
                                                                <div class="flex-1">{{ selectedMail.title }}</div>
                                                            </div>
                                                        </li>
                                                    </ul>
                                                </template>
                                            </Popper>
                                        </div>
                                    </div>
                                </div>
                                <div>
                                    <div class="flex items-center justify-center space-x-3 rtl:space-x-reverse">
                                        <button
                                            type="button"
                                            v-tippy:star
                                            class="enabled:hover:text-warning disabled:opacity-60"
                                            :class="{ 'text-warning': selectedMail.isStar }"
                                            @click="setStar(selectedMail.id)"
                                            :disabled="selectedTab === 'trash'"
                                        >
                                            <icon-star :class="{ 'fill-warning': selectedMail.isStar }" />
                                        </button>
                                        <tippy target="star">Star</tippy>

                                        <button
                                            type="button"
                                            v-tippy:important
                                            class="enabled:hover:text-primary disabled:opacity-60"
                                            :class="{ 'text-primary': selectedMail.isImportant }"
                                            @click="setImportant(selectedMail.id)"
                                            :disabled="selectedTab === 'trash'"
                                        >
                                            <icon-bookmark
                                                :bookmark="false"
                                                class="w-4.5 h-4.5 rotate-90"
                                                :class="{ 'fill-primary': selectedMail.isImportant }"
                                            />
                                        </button>
                                        <tippy target="important">Important</tippy>

                                        <button type="button" v-tippy:reply class="hover:text-info" @click="openMail('reply', selectedMail)">
                                            <icon-arrow-backward class="rtl:hidden" />
                                            <icon-arrow-forward class="ltr:hidden" />
                                        </button>
                                        <tippy target="reply">Reply</tippy>

                                        <button type="button" v-tippy:forward class="hover:text-info" @click="openMail('forward', selectedMail)">
                                            <icon-arrow-backward class="ltr:hidden" />
                                            <icon-arrow-forward class="rtl:hidden" />
                                        </button>
                                        <tippy target="forward">Forward</tippy>
                                    </div>
                                </div>
                            </div>
                            <div
                                class="mt-8 prose dark:prose-p:text-white prose-p:text-sm md:prose-p:text-sm max-w-full prose-img:inline-block prose-img:m-0"
                                v-html="selectedMail.description"
                            ></div>
                            <p class="mt-4">Best Regards,</p>
                            <p>{{ selectedMail.firstName + ' ' + selectedMail.lastName }}</p>

                            <div class="mt-8" v-show="selectedMail.attachments">
                                <div class="text-base mb-4">Attachments</div>
                                <div class="h-px border-b border-[#e0e6ed] dark:border-[#1b2e4b]"></div>
                                <div class="flex items-center flex-wrap mt-6">
                                    <template v-for="(attachment, i) in selectedMail.attachments" :key="i">
                                        <button
                                            type="button"
                                            class="flex items-center ltr:mr-4 rtl:ml-4 mb-4 border border-[#e0e6ed] dark:border-[#1b2e4b] rounded-md hover:text-primary hover:border-primary transition-all duration-300 px-4 py-2.5 relative group"
                                        >
                                            <template v-if="attachment.type === 'image'">
                                                <icon-gallery />
                                            </template>
                                            <template v-if="attachment.type === 'folder'">
                                                <icon-folder />
                                            </template>
                                            <template v-if="attachment.type === 'zip'">
                                                <icon-zip-file />
                                            </template>
                                            <template v-if="attachment.type !== 'zip' && attachment.type !== 'image' && attachment.type !== 'folder'">
                                                <icon-txt-file class="w-5 h-5" />
                                            </template>
                                            <div class="ltr:ml-3 rtl:mr-3">
                                                <p class="text-xs text-primary font-semibold">
                                                    {{ attachment.name }}
                                                </p>
                                                <p class="text-[11px] text-gray-400 dark:text-gray-600">
                                                    {{ attachment.size }}
                                                </p>
                                            </div>
                                            <div
                                                class="bg-dark-light/40 z-[5] w-full h-full absolute ltr:left-0 rtl:right-0 top-0 rounded-md hidden group-hover:block"
                                            ></div>
                                            <div
                                                class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 rounded-full p-1 btn btn-primary hidden group-hover:block z-10"
                                            >
                                                <icon-download class="w-4.5 h-4.5" />
                                            </div>
                                        </button>
                                    </template>
                                </div>
                            </div>
                        </div>
                    </div>
                </template>

                <template v-if="isEdit">
                    <div class="relative">
                        <div class="py-4 px-6 flex items-center">
                            <button type="button" class="xl:hidden hover:text-primary block ltr:mr-3 rtl:ml-3" @click="isShowMailMenu = !isShowMailMenu">
                                <icon-menu />
                            </button>
                            <h4 class="text-lg text-gray-600 dark:text-gray-400 font-medium">Message</h4>
                        </div>
                        <div class="h-px bg-gradient-to-l from-indigo-900/20 via-black dark:via-white to-indigo-900/20 opacity-[0.1]"></div>
                        <form class="p-6 grid gap-6">
                            <div>
                                <input type="text" class="form-input" placeholder="Enter To" v-model="params.to" />
                            </div>

                            <div>
                                <input type="text" class="form-input" placeholder="Enter Cc" v-model="params.cc" />
                            </div>

                            <div>
                                <input type="text" class="form-input" placeholder="Enter Subject" v-model="params.title" />
                            </div>

                            <div class="h-fit">
                                <quillEditor
                                    ref="editor"
                                    v-model:value="params.description"
                                    :options="editorOptions"
                                    style="min-height: 200px"
                                    @ready="quillEditorReady($event)"
                                ></quillEditor>
                            </div>

                            <div>
                                <input
                                    id="file"
                                    type="file"
                                    class="form-input file:py-2 file:px-4 file:border-0 file:font-semibold p-0 file:bg-primary/90 ltr:file:mr-5 rtl:file:ml-5 file:text-white file:hover:bg-primary"
                                    multiple
                                    accept="image/*,.zip,.pdf,.xls,.xlsx,.txt.doc,.docx"
                                    :value="params.file"
                                />
                            </div>

                            <div class="flex items-center ltr:ml-auto rtl:mr-auto mt-8">
                                <button type="button" class="btn btn-outline-danger ltr:mr-3 rtl:ml-3" @click="closeMsgPopUp">Close</button>
                                <button type="button" class="btn btn-success ltr:mr-3 rtl:ml-3" @click="saveMail('save', null)">Save</button>
                                <button type="button" class="btn btn-primary" @click="saveMail('send', params.id)">Send</button>
                            </div>
                        </form>
                    </div>
                </template>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import { ref, computed, onMounted } from 'vue';
    import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue';
    import { quillEditor } from 'vue3-quill';
    import 'vue3-quill/lib/vue3-quill.css';
    import Swal from 'sweetalert2';
    import { useAppStore } from '@/stores/index';
    import { useMeta } from '@/composables/use-meta';

    import IconMail from '@/components/icon/icon-mail.vue';
    import IconStar from '@/components/icon/icon-star.vue';
    import IconSend from '@/components/icon/icon-send.vue';
    import IconInfoHexagon from '@/components/icon/icon-info-hexagon.vue';
    import IconFile from '@/components/icon/icon-file.vue';
    import IconTrashLines from '@/components/icon/icon-trash-lines.vue';
    import IconCaretDown from '@/components/icon/icon-caret-down.vue';
    import IconArchive from '@/components/icon/icon-archive.vue';
    import IconBookmark from '@/components/icon/icon-bookmark.vue';
    import IconVideo from '@/components/icon/icon-video.vue';
    import IconChartSquare from '@/components/icon/icon-chart-square.vue';
    import IconUserPlus from '@/components/icon/icon-user-plus.vue';
    import IconPlus from '@/components/icon/icon-plus.vue';
    import IconRefresh from '@/components/icon/icon-refresh.vue';
    import IconWheel from '@/components/icon/icon-wheel.vue';
    import IconHorizontalDots from '@/components/icon/icon-horizontal-dots.vue';
    import IconOpenBook from '@/components/icon/icon-open-book.vue';
    import IconBook from '@/components/icon/icon-book.vue';
    import IconTrash from '@/components/icon/icon-trash.vue';
    import IconRestore from '@/components/icon/icon-restore.vue';
    import IconMenu from '@/components/icon/icon-menu.vue';
    import IconSearch from '@/components/icon/icon-search.vue';
    import IconSettings from '@/components/icon/icon-settings.vue';
    import IconHelpCircle from '@/components/icon/icon-help-circle.vue';
    import IconUser from '@/components/icon/icon-user.vue';
    import IconMessage2 from '@/components/icon/icon-message-2.vue';
    import IconUsers from '@/components/icon/icon-users.vue';
    import IconTag from '@/components/icon/icon-tag.vue';
    import IconPaperclip from '@/components/icon/icon-paperclip.vue';
    import IconArrowLeft from '@/components/icon/icon-arrow-left.vue';
    import IconPrinter from '@/components/icon/icon-printer.vue';
    import IconArrowBackward from '@/components/icon/icon-arrow-backward.vue';
    import IconArrowForward from '@/components/icon/icon-arrow-forward.vue';
    import IconGallery from '@/components/icon/icon-gallery.vue';
    import IconFolder from '@/components/icon/icon-folder.vue';
    import IconZipFile from '@/components/icon/icon-zip-file.vue';
    import IconDownload from '@/components/icon/icon-download.vue';
    import IconTxtFile from '@/components/icon/icon-txt-file.vue';


    useMeta({ title: 'Mailbox' });
    const store = useAppStore();

    const defaultData = ref({
        id: null,
        from: 'vristo@mail.com',
        to: '',
        cc: '',
        title: '',
        file: null,
        description: '',
        displayDescription: '',
    });
    const isShowMailMenu = ref(false);
    const isEdit = ref(false);
    const selectedTab = ref('inbox');
    const filteredMailList: any = ref([]);
    const ids: any = ref([]);
    const searchText = ref('');
    const selectedMail: any = ref(null);
    const params: any = ref(defaultData.value);
    const mailList = ref([
        {
            id: 1,
            path: 'profile-15.jpeg',
            firstName: 'Laurie',
            lastName: 'Fox',
            email: 'laurieFox@mail.com',
            date: new Date(),
            time: '2:00 PM',
            title: 'Promotion Page',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: false,
            isStar: true,
            group: 'social',
            isUnread: false,
            attachments: [
                {
                    name: 'Confirm File.txt',
                    size: '450KB',
                    type: 'file',
                },
                {
                    name: 'Important Docs.xml',
                    size: '2.1MB',
                    type: 'file',
                },
            ],
            description: `
                        <p class="mail-content"> Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <div class="gallery text-center">
                            <img alt="image-gallery" src="${'/assets/images/carousel3.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;" />
                            <img alt="image-gallery" src="${'/assets/images/carousel2.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;" />
                            <img alt="image-gallery" src="${'/assets/images/carousel1.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;" />
                        </div>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 2,
            path: 'profile-14.jpeg',
            firstName: 'Andy',
            lastName: 'King',
            email: 'kingAndy@mail.com',
            date: new Date(),
            time: '6:28 PM',
            title: 'Hosting Payment Reminder',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 3,
            path: '',
            firstName: 'Kristen',
            lastName: 'Beck',
            email: 'kirsten.beck@mail.com',
            date: new Date(),
            time: '11:09 AM',
            title: 'Verification Link',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: 'social',
            isUnread: true,
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 4,
            path: 'profile-16.jpeg',
            firstName: 'Christian',
            lastName: '',
            email: 'christian@mail.com',
            date: '11/30/2021',
            time: '2:00 PM',
            title: 'New Updates',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: 'private',
            isUnread: false,
            attachments: [
                {
                    name: 'update.zip',
                    size: '1.38MB',
                    type: 'zip',
                },
            ],
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 5,
            path: 'profile-17.jpeg',
            firstName: 'Roxanne',
            lastName: '',
            email: 'roxanne@mail.com',
            date: '11/15/2021',
            time: '2:00 PM',
            title: 'Schedular Alert',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: 'personal',
            isUnread: true,
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 6,
            path: 'profile-18.jpeg',
            firstName: 'Nia',
            lastName: 'Hillyer',
            email: 'niahillyer@mail.com',
            date: '08/16/2020',
            time: '2:22 AM',
            title: 'Motion UI Kit',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: true,

            isStar: true,
            group: '',
            isUnread: false,
            description: `
                        <p class="mail-content"> Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et.</p>
                        <div class="gallery text-center">
                            <img alt="image-gallery" src="${'/assets/images/carousel3.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;">
                            <img alt="image-gallery" src="${'/assets/images/carousel2.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;">
                            <img alt="image-gallery" src="${'/assets/images/carousel1.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;">
                        </div>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 7,
            path: 'profile-19.jpeg',
            firstName: 'Iris',
            lastName: 'Hubbard',
            email: 'irishubbard@mail.com',
            date: '08/16/2020',
            time: '1:40 PM',
            title: 'Green Illustration',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: true,

            isStar: true,
            group: '',
            isUnread: false,
            description: `
                        <p class="mail-content"> Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 8,
            path: '',
            firstName: 'Ernest',
            lastName: 'Reeves',
            email: 'reevesErnest@mail.com',
            date: '06/02/2020',
            time: '8:25 PM',
            title: 'Youtube',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'archive',
            isImportant: true,

            isStar: true,
            group: 'work',
            isUnread: false,
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 9,
            path: 'profile-20.jpeg',
            firstName: 'Info',
            lastName: 'Company',
            email: 'infocompany@mail.com',
            date: '02/10/2020',
            time: '7:00 PM',
            title: '50% Discount',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: 'work',
            isUnread: false,
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },

        {
            id: 10,
            path: '',
            firstName: 'NPM',
            lastName: 'Inc',
            email: 'npminc@mail.com',
            date: '12/15/2018',
            time: '8:37 AM',
            title: 'npm Inc',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'archive',
            isImportant: false,
            isStar: false,
            group: 'personal',
            isUnread: true,
            attachments: [
                {
                    name: 'package.zip',
                    size: '450KB',
                    type: 'zip',
                },
            ],
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 11,
            path: 'profile-21.jpeg',
            firstName: 'Marlene',
            lastName: 'Wood',
            email: 'marlenewood@mail.com',
            date: '11/25/2018',
            time: '1:51 PM',
            title: 'eBill',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: 'personal',
            isUnread: false,
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },

        {
            id: 12,
            path: '',
            firstName: 'Keith',
            lastName: 'Foster',
            email: 'kf@mail.com',
            date: '12/15/2018',
            time: '9:30 PM',
            title: 'Web Design News',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'draft',
            isImportant: false,
            isStar: false,
            group: 'personal',
            isUnread: false,
            description: `
                        <p class="mail-content"> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.</p>
                        `,
        },
        {
            id: 13,
            path: '',
            firstName: 'Amy',
            lastName: 'Diaz',
            email: 'amyDiaz@mail.com',
            date: '12/15/2018',
            time: '2:00 PM',
            title: 'Ecommerce Analytics',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'draft',
            isImportant: false,
            isStar: false,
            group: 'private',
            isUnread: false,
            description: `
                        <p class="mail-content"> Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue. Vivamus sem ante, ultrices at ex a, rhoncus ullamcorper tellus. Nunc iaculis eu ligula ac consequat. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Vestibulum mattis urna neque, eget posuere lorem tempus non. Suspendisse ac turpis dictum, convallis est ut, posuere sem. Etiam imperdiet aliquam risus, eu commodo urna vestibulum at. Suspendisse malesuada lorem eu sodales aliquam.</p>
                        `,
        },

        {
            id: 14,
            path: '',
            firstName: 'Alan',
            lastName: '',
            email: 'alan@mail.com',
            date: '12/16/2019',
            time: '8:45 AM',
            title: 'Mozilla Update',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'sent_mail',
            isImportant: false,
            isStar: false,
            group: 'work',
            isUnread: false,
            attachments: [
                {
                    name: 'Confirm File',
                    size: '450KB',
                    type: 'file',
                },
                {
                    name: 'Important Docs',
                    size: '2.1MB',
                    type: 'folder',
                },
                {
                    name: 'Photo.png',
                    size: '50kb',
                    type: 'image',
                },
            ],
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 15,
            path: '',
            firstName: 'Justin',
            lastName: 'Cross',
            email: 'justincross@mail.com',
            date: '09/14/219',
            time: '3:10 PM',
            title: 'App Project Checklist',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'sent_mail',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            attachments: [
                {
                    name: 'Important Docs',
                    size: '2.1MB',
                    type: 'folder',
                },
                {
                    name: 'Photo.png',
                    size: '50kb',
                    type: 'image',
                },
            ],
            description: `
                        <p class="mail-content"> Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },

        {
            id: 16,
            path: 'profile-21.jpeg',
            firstName: 'Alex',
            lastName: 'Gray',
            email: 'alexGray@mail.com',
            date: '08/16/2019',
            time: '10:18 AM',
            title: 'Weekly Newsletter',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'spam',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            attachments: [
                {
                    name: 'Confirm File',
                    size: '450KB',
                    type: 'file',
                },
                {
                    name: 'Important Docs',
                    size: '2.1MB',
                    type: 'folder',
                },
                {
                    name: 'Photo.png',
                    size: '50kb',
                    type: 'image',
                },
            ],
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 17,
            path: 'profile-22.jpeg',
            firstName: 'Info',
            lastName: 'Company',
            email: 'infocompany@mail.com',
            date: '02/10/2018',
            time: '7:00 PM',
            title: '50% Discount',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'spam',
            isImportant: false,
            isStar: false,
            group: 'work',
            isUnread: false,
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 18,
            path: 'profile-21.jpeg',
            firstName: 'Marlene',
            lastName: 'Wood',
            email: 'marlenewood@mail.com',
            date: '11/25/2017',
            time: '1:51 PM',
            title: 'eBill',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'spam',
            isImportant: false,
            isStar: false,
            group: 'personal',
            isUnread: false,
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },

        {
            id: 19,
            path: 'profile-23.jpeg',
            firstName: 'Ryan MC',
            lastName: 'Killop',
            email: 'ryanMCkillop@mail.com',
            date: '08/17/2018',
            time: '11:45 PM',
            title: 'Make it Simple',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'trash',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `
                        <p class="mail-content"> Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <div class="gallery text-center">
                            <img alt="image-gallery" src="${'/assets/images/carousel2.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;">
                            <img alt="image-gallery" src="${'/assets/images/carousel3.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;">
                            <img alt="image-gallery" src="${'/assets/images/carousel1.jpeg'}" class="mb-4 mt-4" style="width: 250px; height: 180px;">
                        </div>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 20,
            path: 'profile-23.jpeg',
            firstName: 'Liam',
            lastName: 'Sheldon',
            email: 'liamsheldon@mail.com',
            date: '08/17/2018 ',
            time: '11:45 PM',
            title: 'New Offers',
            displayDescription:
                'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi pulvinar feugiat consequat. Duis lacus nibh, sagittis id varius vel, aliquet non augue.',
            type: 'trash',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            attachments: [
                {
                    name: 'Confirm File',
                    size: '450KB',
                    type: 'file',
                },
            ],
            description: `
                        <p class="mail-content"> Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS. </p>
                        <p>Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.</p>
                        `,
        },
        {
            id: 21,
            path: 'profile-21.jpeg',
            firstName: 'Porter',
            lastName: 'Taylor',
            email: 'porter.harber@wiza.info',
            date: '06/01/2020',
            time: '02:40 PM',
            title: 'Id labore ex et quam laborum',
            displayDescription:
                'Laudantium enim quasi est quidem magnam voluptate ipsam eos\ntempora quo necessitatibus\ndolor quam autem quasi\nreiciendis et nam sapiente accusantium',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content">Laudantium enim quasi est quidem magnam voluptate ipsam eos\ntempora quo necessitatibus\ndolor quam autem quasi\nreiciendis et nam sapiente accusantium</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 22,
            path: 'profile-22.jpeg',
            firstName: 'Brock',
            lastName: 'Mills',
            email: 'brock.gibson@farrell.biz',
            date: '09/08/2020',
            time: '04:20 AM',
            title: 'Quo vero reiciendis velit similique earum',
            displayDescription:
                'Est natus enim nihil est dolore omnis voluptatem numquam\net omnis occaecati quod ullam at\nvoluptatem error expedita pariatur\nnihil sint nostrum voluptatem reiciendis et',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content">Est natus enim nihil est dolore omnis voluptatem numquam\net omnis occaecati quod ullam at\nvoluptatem error expedita pariatur\nnihil sint nostrum voluptatem reiciendis et</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 23,
            path: 'profile-3.jpeg',
            firstName: 'Nyost',
            lastName: 'Terry',
            email: 'nyost@yahoo.com',
            date: '04/01/2019',
            time: '02:10 AM',
            title: 'Odio adipisci rerum aut animi',
            displayDescription:
                'Quia molestiae reprehenderit quasi aspernatur\naut expedita occaecati aliquam eveniet laudantium\nomnis quibusdam delectus saepe quia accusamus maiores nam est\ncum et ducimus et vero voluptates excepturi deleniti ratione',
            type: 'inbox',
            isImportant: true,
            isStar: false,
            group: 'personal',
            isUnread: false,
            description: `<p class="mail-content">Quia molestiae reprehenderit quasi aspernatur\naut expedita occaecati aliquam eveniet laudantium\nomnis quibusdam delectus saepe quia accusamus maiores nam est\ncum et ducimus et vero voluptates excepturi deleniti ratione</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 24,
            path: 'profile-2.jpeg',
            firstName: 'Leonardo',
            lastName: 'Knox',
            email: 'leonardo61@yahoo.com',
            date: '08/08/2018',
            time: '07:50 PM',
            title: 'Alias odio sit',
            displayDescription:
                'Non et atque\noccaecati deserunt quas accusantium unde odit nobis qui voluptatem\nquia voluptas consequuntur itaque dolor\net qui rerum deleniti ut occaecati',
            type: 'inbox',
            isImportant: false,
            isStar: true,
            group: '',
            isUnread: false,
            description: `<p class="mail-content">Non et atque\noccaecati deserunt quas accusantium unde odit nobis qui voluptatem\nquia voluptas consequuntur itaque dolor\net qui rerum deleniti ut occaecati</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 25,
            path: 'profile-24.jpeg',
            firstName: 'Melisa',
            lastName: 'Mitchell',
            email: 'melisa.legros@mayer.com',
            date: '10/03/2018',
            time: '06:40 AM',
            title: 'Vero eaque aliquid doloribus et culpa',
            displayDescription:
                'Harum non quasi et ratione\ntempore iure ex voluptates in ratione\nharum architecto fugit inventore cupiditate\nvoluptates magni quo et',
            type: 'inbox',
            isImportant: true,
            isStar: true,
            group: 'work',
            isUnread: false,
            description: `<p class="mail-content">Harum non quasi et ratione\ntempore iure ex voluptates in ratione\nharum architecto fugit inventore cupiditate\nvoluptates magni quo et</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 26,
            path: 'profile-26.jpeg',
            firstName: 'Florida',
            lastName: 'Morgan',
            email: 'florida54@gmail.com',
            date: '05/12/2019',
            time: '09:20 PM',
            title: 'Et fugit eligendi deleniti quidem qui sint nihil autem',
            displayDescription:
                'Doloribus at sed quis culpa deserunt consectetur qui praesentium\naccusamus fugiat dicta\nvoluptatem rerum ut voluptate autem\nvoluptatem repellendus aspernatur dolorem in',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content">Doloribus at sed quis culpa deserunt consectetur qui praesentium\naccusamus fugiat dicta\nvoluptatem rerum ut voluptate autem\nvoluptatem repellendus aspernatur dolorem in</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 27,
            path: 'profile-27.jpeg',
            firstName: 'Madison',
            lastName: 'King',
            email: 'madison86@yahoo.com',
            date: '12/04/2018',
            time: '10:40 PM',
            title: 'Repellat consequatur praesentium vel minus molestias voluptatum',
            displayDescription:
                'Maiores sed dolores similique labore et inventore et\nquasi temporibus esse sunt id et\neos voluptatem aliquam\naliquid ratione corporis molestiae mollitia quia et magnam dolor',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: 'private',
            isUnread: false,
            description: `<p class="mail-content">Maiores sed dolores similique labore et inventore et\nquasi temporibus esse sunt id et\neos voluptatem aliquam\naliquid ratione corporis molestiae mollitia quia et magnam dolor</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 28,
            path: 'profile-30.jpeg',
            firstName: 'Paul',
            lastName: 'Lambert',
            email: 'paul.cruickshank@yahoo.com',
            date: '06/05/2018',
            time: '01:40 AM',
            title: 'Et omnis dolorem',
            displayDescription:
                'Ut voluptatem corrupti velit\nad voluptatem maiores\net nisi velit vero accusamus maiores\nvoluptates quia aliquid ullam eaque',
            type: 'inbox',
            isImportant: true,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content">Ut voluptatem corrupti velit\nad voluptatem maiores\net nisi velit vero accusamus maiores\nvoluptates quia aliquid ullam eaque</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 29,
            path: 'profile-31.jpeg',
            firstName: 'Brakus',
            lastName: 'Morrison',
            email: 'brakus.heidi@gmail.com',
            date: '03/09/2018',
            time: '06:10 PM',
            title: 'Provident id voluptas',
            displayDescription:
                'Sapiente assumenda molestiae atque\nadipisci laborum distinctio aperiam et ab ut omnis\net occaecati aspernatur odit sit rem expedita\nquas enim ipsam minus',
            type: 'inbox',
            isImportant: false,
            isStar: true,
            group: 'social',
            isUnread: false,
            description: `<p class="mail-content">Sapiente assumenda molestiae atque\nadipisci laborum distinctio aperiam et ab ut omnis\net occaecati aspernatur odit sit rem expedita\nquas enim ipsam minus</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 30,
            path: 'profile-32.jpeg',
            firstName: 'Predovic',
            lastName: 'Peake',
            email: 'predovic.arianna@kirlin.com',
            date: '05/06/2018',
            time: '09:00 AM',
            title: 'Eaque et deleniti atque tenetur ut quo ut',
            displayDescription:
                'Voluptate iusto quis nobis reprehenderit ipsum amet nulla\nquia quas dolores velit et non\naut quia necessitatibus\nnostrum quaerat nulla et accusamus nisi facili',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: 'personal',
            isUnread: false,
            description: `<p class="mail-content">Voluptate iusto quis nobis reprehenderit ipsum amet nulla\nquia quas dolores velit et non\naut quia necessitatibus\nnostrum quaerat nulla et accusamus nisi facili</p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 31,
            path: 'profile-32.jpeg',
            firstName: 'shaylee',
            lastName: 'Buford',
            email: 'Buford@shaylee.biz',
            date: '07/03/2018',
            time: '08:15 AM',
            title: 'Ex velit ut cum eius odio ad placeat',
            displayDescription:
                'Quia incidunt ut\naliquid est ut rerum deleniti iure est\nipsum quia ea sint et\nvoluptatem quaerat eaque repudiandae eveniet aut',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content"></p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 32,
            path: 'profile-32.jpeg',
            firstName: 'Maria',
            lastName: 'laurel',
            email: 'Maria@laurel.name',
            date: '08/03/2018',
            time: '09:30 AM',
            title: 'Dolorem architecto ut pariatur quae qui suscipit',
            displayDescription:
                'Nihil ea itaque libero illo\nofficiis quo quo dicta inventore consequatur voluptas voluptatem\ncorporis sed necessitatibus velit tempore\nrerum velit et temporibus',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content"></p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 33,
            path: 'profile-32.jpeg',
            firstName: 'Jaeden',
            lastName: 'Towne',
            email: 'Jaeden.Towne@arlene.tv',
            date: '11/07/2018',
            time: '10:15 AM',
            title: 'Voluptatum totam vel voluptate omnis',
            displayDescription: 'Fugit harum quae vero\nlibero unde tempore\nsoluta eaque culpa sequi quibusdam nulla id\net et necessitatibus',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content"></p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 34,
            path: 'profile-32.jpeg',
            firstName: 'Schneider',
            lastName: 'Ethelyn',
            email: 'Ethelyn.Schneider@emelia.co.uk',
            date: '07/11/2018',
            time: '10:30 AM',
            title: 'Omnis nemo sunt ab autem',
            displayDescription: 'Omnis temporibus quasi ab omnis\nfacilis et omnis illum quae quasi aut\nminus iure ex rem ut reprehenderit\nin non fugit',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content"></p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
        {
            id: 35,
            path: 'profile-32.jpeg',
            firstName: 'Anna',
            lastName: 'Georgi',
            email: 'Georgianna@florence.io',
            date: '10/10/2017',
            time: '10:45 AM',
            title: 'Repellendus sapiente omnis praesentium aliquam ipsum id molestiae omnis',
            displayDescription: 'Dolor mollitia quidem facere et\nvel est ut\nut repudiandae est quidem dolorem sed atque\nrem quia aut adipisci sunt',
            type: 'inbox',
            isImportant: false,
            isStar: false,
            group: '',
            isUnread: false,
            description: `<p class="mail-content"></p>
                    <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>`,
        },
    ]);
    const pager = ref({
        currentPage: 1,
        totalPages: 0,
        pageSize: 10,
        startIndex: 0,
        endIndex: 0,
    });
    const pagedMails: any = ref([]);
    const editorOptions = ref({
        modules: {
            toolbar: [[{ header: [1, 2, false] }], ['bold', 'italic', 'underline', 'link'], [{ list: 'ordered' }, { list: 'bullet' }], ['clean']],
        },
        placeholder: '',
    });
    const quillEditorObj: any = ref(null);

    const checkAllCheckbox = computed(() => {
        if (filteredMailList.value.length && ids.value.length === filteredMailList.value.length) {
            return true;
        } else {
            return false;
        }
    });
    const showTime = (item: any) => {
        const displayDt: any = new Date(item.date);
        const cDt: any = new Date();
        if (displayDt.toDateString() === cDt.toDateString()) {
            return item.time;
        } else {
            if (displayDt.getFullYear() === cDt.getFullYear()) {
                var monthNames = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
                return monthNames[displayDt.getMonth()] + ' ' + String(displayDt.getDate()).padStart(2, '0');
            } else {
                return String(displayDt.getMonth() + 1).padStart(2, '0') + '/' + String(displayDt.getDate()).padStart(2, '0') + '/' + displayDt.getFullYear();
            }
        }
    };

    const checkAll = (isChecked: boolean = false) => {
        if (isChecked) {
            ids.value = filteredMailList.value.map((d: any) => {
                return d.id;
            });
        } else {
            clearSelection();
        }
    };

    onMounted(() => {
        searchMails();
    });

    const quillEditorReady = (quill: any) => {
        quillEditorObj.value = quill;
    };

    const searchMails = (isResetPage = true) => {
        if (isResetPage) {
            pager.value.currentPage = 1;
        }

        let res;
        if (selectedTab.value === 'important') {
            res = mailList.value.filter((d) => d.isImportant);
        } else if (selectedTab.value === 'star') {
            res = mailList.value.filter((d) => d.isStar);
        } else if (selectedTab.value === 'personal' || selectedTab.value === 'work' || selectedTab.value === 'social' || selectedTab.value === 'private') {
            res = mailList.value.filter((d) => d.group === selectedTab.value);
        } else {
            res = mailList.value.filter((d) => d.type === selectedTab.value);
        }
        filteredMailList.value = res.filter(
            (d) =>
                (d.title && d.title.toLowerCase().includes(searchText.value)) ||
                (d.firstName && d.firstName.toLowerCase().includes(searchText.value)) ||
                (d.lastName && d.lastName.toLowerCase().includes(searchText.value)) ||
                (d.displayDescription && d.displayDescription.toLowerCase().includes(searchText.value))
        );
        if (filteredMailList.value.length) {
            pager.value.totalPages = pager.value.pageSize < 1 ? 1 : Math.ceil(filteredMailList.value.length / pager.value.pageSize);
            if (pager.value.currentPage > pager.value.totalPages) {
                pager.value.currentPage = 1;
            }
            pager.value.startIndex = (pager.value.currentPage - 1) * pager.value.pageSize;
            pager.value.endIndex = Math.min(pager.value.startIndex + pager.value.pageSize - 1, filteredMailList.value.length - 1);
            pagedMails.value = filteredMailList.value.slice(pager.value.startIndex, pager.value.endIndex + 1);
        } else {
            pagedMails.value = [];
            pager.value.startIndex = -1;
            pager.value.endIndex = -1;
        }
        clearSelection();
    };

    const clearSelection = () => {
        ids.value = [];
    };

    const tabChanged = (tabType: any) => {
        isEdit.value = false;
        selectedTab.value = tabType;
        isShowMailMenu.value = false;
        selectedMail.value = null;
        searchMails();
    };

    const setImportant = (mailId: number) => {
        if (mailId) {
            let item = filteredMailList.value.find((d: any) => d.id === mailId);
            item.isImportant = !item.isImportant;
            setTimeout(() => {
                searchMails(false);
            });
        }
    };

    const setStar = (mailId: number) => {
        if (mailId) {
            let item = filteredMailList.value.find((d: any) => d.id === mailId);
            item.isStar = !item.isStar;
            setTimeout(() => {
                searchMails(false);
            });
        }
    };

    const refreshMails = () => {
        searchText.value = '';
        searchMails(false);
    };

    const setSpam = () => {
        if (ids.value.length) {
            let items = filteredMailList.value.filter((d: any) => ids.value.includes(d.id));
            for (let item of items) {
                item.type = item.type === 'spam' ? 'inbox' : 'spam';
            }
            if (selectedTab.value == 'spam') {
                showMessage(ids.value.length + ' Mail has been removed from Spam.');
            } else {
                showMessage(ids.value.length + ' Mail has been added to Spam.');
            }
            searchMails(false);
        }
    };

    const setArchive = () => {
        if (ids.value.length) {
            let items = filteredMailList.value.filter((d: any) => ids.value.includes(d.id));
            for (let item of items) {
                item.type = item.type === 'archive' ? 'inbox' : 'archive';
            }
            if (selectedTab.value == 'archive') {
                showMessage(ids.value.length + ' Mail has been removed from Archive.');
            } else {
                showMessage(ids.value.length + ' Mail has been added to Archive.');
            }
            searchMails(false);
        }
    };

    const setGroup = (group: any) => {
        if (ids.value.length) {
            let items = filteredMailList.value.filter((d: any) => ids.value.includes(d.id));
            for (let item of items) {
                item.group = group;
            }

            showMessage(ids.value.length + ' Mail has been grouped as ' + group.toUpperCase());
            clearSelection();
            setTimeout(() => {
                searchMails(false);
            });
        }
    };

    const setAction = (type: any) => {
        if (ids.value.length) {
            const totalSelected = ids.value.length;
            let items = filteredMailList.value.filter((d: any) => ids.value.includes(d.id));
            for (let item of items) {
                if (type === 'trash') {
                    item.type = 'trash';
                    item.group = '';
                    item.isStar = false;
                    item.isImportant = false;
                    showMessage(totalSelected + ' Mail has been deleted.');
                    searchMails(false);
                } else if (type === 'read') {
                    item.isUnread = false;
                    showMessage(totalSelected + ' Mail has been marked as Read.');
                } else if (type === 'unread') {
                    item.isUnread = true;
                    showMessage(totalSelected + ' Mail has been marked as UnRead.');
                } else if (type === 'important') {
                    item.isImportant = true;
                    showMessage(totalSelected + ' Mail has been marked as Important.');
                } else if (type === 'unimportant') {
                    item.isImportant = false;
                    showMessage(totalSelected + ' Mail has been marked as UnImportant.');
                } else if (type === 'star') {
                    item.isStar = true;
                    showMessage(totalSelected + ' Mail has been marked as Star.');
                }
                //restore & permanent delete
                else if (type === 'restore') {
                    item.type = 'inbox';
                    showMessage(totalSelected + ' Mail Restored.');
                    searchMails(false);
                } else if (type === 'delete') {
                    mailList.value = mailList.value.filter((d: any) => d.id != item.id);
                    showMessage(totalSelected + ' Mail Permanently Deleted.');
                    searchMails(false);
                }
            }
            clearSelection();
        }
    };

    const saveMail = (type: any, id: any) => {
        if (!params.value.to) {
            showMessage('To email address is required.', 'error');
            return false;
        }
        if (!params.value.title) {
            showMessage('Title of email is required.', 'error');
            return false;
        }

        let maxId = 0;
        if (!params.value.id) {
            maxId = mailList.value.length ? mailList.value.reduce((max, character) => (character.id > max ? character.id : max), mailList.value[0].id) : 0;
        }
        let cDt = new Date();

        let obj: any = {
            id: maxId + 1,
            path: '',
            firstName: '',
            lastName: '',
            email: params.value.to,
            date: cDt.getMonth() + 1 + '/' + cDt.getDate() + '/' + cDt.getFullYear(),
            time: cDt.toLocaleTimeString(),
            title: params.value.title,
            displayDescription: quillEditorObj.value.getText(),
            type: 'draft',
            isImportant: false,
            group: '',
            isUnread: false,
            description: params.value.description,
            attachments: null,
        };
        if (params.value.file && params.value.file.length) {
            obj.attachments = [];
            for (let file of params.value.file) {
                let flObj = {
                    name: file.name,
                    size: getFileSize(file.size),
                    type: getFileType(file.type),
                };
                obj.attachments.push(flObj);
            }
        }
        if (type === 'save' || type === 'save_reply' || type === 'save_forward') {
            //saved to draft

            obj.type = 'draft';
            mailList.value.splice(0, 0, obj);
            searchMails();

            showMessage('Mail has been saved successfully to draft.');
        } else if (type === 'send' || type === 'reply' || type === 'forward') {
            //saved to sent mail

            obj.type = 'sent_mail';
            mailList.value.splice(0, 0, obj);
            searchMails();

            showMessage('Mail has been sent successfully.');
        }

        selectedMail.value = null;
        isEdit.value = false;
    };

    const getFileSize = (file_type: any) => {
        let type = 'file';
        if (file_type.includes('image/')) {
            type = 'image';
        } else if (file_type.includes('application/x-zip')) {
            type = 'zip';
        }
        return type;
    };

    const getFileType = (total_bytes: number) => {
        let size = '';
        if (total_bytes < 1000000) {
            size = Math.floor(total_bytes / 1000) + 'KB';
        } else {
            size = Math.floor(total_bytes / 1000000) + 'MB';
        }
        return size;
    };

    const selectMail = (item: any) => {
        if (item) {
            if (item.type != 'draft') {
                if (item && item.isUnread) {
                    item.isUnread = false;
                }
                selectedMail.value = item;
            } else {
                openMail('draft', item);
            }
        } else {
            selectedMail.value = '';
        }
    };

    const openMail = (type: string, item: any) => {
        if (type === 'add') {
            isShowMailMenu.value = false;
            params.value = JSON.parse(JSON.stringify(defaultData.value));
        } else if (type === 'draft') {
            let data = JSON.parse(JSON.stringify(item));
            params.value = data;
            params.value.from = defaultData.value.from;
            params.value.to = data.email;
            params.value.displayDescription = data.email;
        } else if (type === 'reply') {
            let data = JSON.parse(JSON.stringify(item));
            params.value = data;
            params.value.from = defaultData.value.from;
            params.value.to = data.email;
            params.value.title = 'Re: ' + params.value.title;
            params.value.displayDescription = 'Re: ' + params.value.title;
        } else if (type === 'forward') {
            let data = JSON.parse(JSON.stringify(item));
            params.value = data;
            params.value.from = defaultData.value.from;
            params.value.to = data.email;
            params.value.title = 'Fwd: ' + params.value.title;
            params.value.displayDescription = 'Fwd: ' + params.value.title;
        }
        isEdit.value = true;
    };

    const closeMsgPopUp = () => {
        isEdit.value = false;
        selectedTab.value = 'inbox';
        searchMails();
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
