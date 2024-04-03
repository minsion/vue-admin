<template>
    <div :class="{ 'dark text-white-dark': store.semidark }">
        <nav class="sidebar fixed min-h-screen h-full top-0 bottom-0 w-[260px] shadow-[5px_0_25px_0_rgba(94,92,154,0.1)] z-50 transition-all duration-300">
            <div class="bg-white dark:bg-[#0e1726] h-full">
                <div class="flex justify-between items-center px-4 py-3">
                    <router-link to="/" class="main-logo flex items-center shrink-0">
                        <img class="w-8 ml-[5px] flex-none" src="/assets/images/logo.svg" alt="" />
                        <span class="text-2xl ltr:ml-1.5 rtl:mr-1.5 font-semibold align-middle lg:inline dark:text-white-light">VRISTO</span>
                    </router-link>
                    <a
                        href="javascript:;"
                        class="collapse-icon w-8 h-8 rounded-full flex items-center hover:bg-gray-500/10 dark:hover:bg-dark-light/10 dark:text-white-light transition duration-300 rtl:rotate-180 hover:text-primary"
                        @click="store.toggleSidebar()"
                    >
                        <icon-carets-down class="m-auto rotate-90" />
                    </a>
                </div>
                <perfect-scrollbar
                    :options="{
                        swipeEasing: true,
                        wheelPropagation: false,
                    }"
                    class="h-[calc(100vh-80px)] relative"
                >
                    <ul class="relative font-semibold space-y-0.5 p-4 py-0">
                        <li class="menu nav-item">
                            <button
                                type="button"
                                class="nav-link group w-full"
                                :class="{ active: activeDropdown === 'dashboard' }"
                                @click="activeDropdown === 'dashboard' ? (activeDropdown = null) : (activeDropdown = 'dashboard')"
                            >
                                <div class="flex items-center">
                                    <icon-menu-dashboard class="group-hover:!text-primary shrink-0" />
                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">
                                        {{ $t('dashboard') }}
                                    </span>
                                </div>
                                <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'dashboard' }">
                                    <icon-caret-down />
                                </div>
                            </button>
                            <vue-collapsible :isOpen="activeDropdown === 'dashboard'">
                                <ul class="sub-menu text-gray-500">
                                    <li>
                                        <router-link to="/" @click="toggleMobileMenu">{{ $t('sales') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/analytics" @click="toggleMobileMenu">{{ $t('analytics') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/finance" @click="toggleMobileMenu">{{ $t('finance') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/crypto" @click="toggleMobileMenu">{{ $t('crypto') }}</router-link>
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>

                        <h2 class="py-3 px-7 flex items-center uppercase font-extrabold bg-white-light/30 dark:bg-dark dark:bg-opacity-[0.08] -mx-4 mb-1">
                            <icon-minus class="w-4 h-5 flex-none hidden" />
                            <span>{{ $t('apps') }}</span>
                        </h2>

                        <li class="nav-item">
                            <ul>
                                <li class="nav-item">
                                    <router-link to="/apps/chat" class="group" @click="toggleMobileMenu">
                                        <div class="flex items-center">
                                            <icon-menu-chat class="group-hover:!text-primary shrink-0" />

                                            <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                                $t('chat')
                                            }}</span>
                                        </div>
                                    </router-link>
                                </li>
                                <li class="nav-item">
                                    <router-link to="/apps/mailbox" class="group" @click="toggleMobileMenu">
                                        <div class="flex items-center">
                                            <icon-menu-mailbox class="group-hover:!text-primary shrink-0" />

                                            <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                                $t('mailbox')
                                            }}</span>
                                        </div>
                                    </router-link>
                                </li>
                                <li class="nav-item">
                                    <router-link to="/apps/todolist" class="group" @click="toggleMobileMenu">
                                        <div class="flex items-center">
                                            <icon-menu-todo class="group-hover:!text-primary shrink-0" />

                                            <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                                $t('todo_list')
                                            }}</span>
                                        </div>
                                    </router-link>
                                </li>
                                <li class="nav-item">
                                    <router-link to="/apps/notes" class="group" @click="toggleMobileMenu">
                                        <div class="flex items-center">
                                            <icon-menu-notes class="group-hover:!text-primary shrink-0" />

                                            <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                                $t('notes')
                                            }}</span>
                                        </div>
                                    </router-link>
                                </li>
                                <li class="nav-item">
                                    <router-link to="/apps/scrumboard" class="group" @click="toggleMobileMenu">
                                        <div class="flex items-center">
                                            <icon-menu-scrumboard class="group-hover:!text-primary shrink-0" />

                                            <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                                $t('scrumboard')
                                            }}</span>
                                        </div>
                                    </router-link>
                                </li>
                                <li class="nav-item">
                                    <router-link to="/apps/contacts" class="group" @click="toggleMobileMenu">
                                        <div class="flex items-center">
                                            <icon-menu-contacts class="group-hover:!text-primary shrink-0" />

                                            <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                                $t('contacts')
                                            }}</span>
                                        </div>
                                    </router-link>
                                </li>

                                <li class="menu nav-item">
                                    <button
                                        type="button"
                                        class="nav-link group w-full"
                                        :class="{ active: activeDropdown === 'invoice' }"
                                        @click="activeDropdown === 'invoice' ? (activeDropdown = null) : (activeDropdown = 'invoice')"
                                    >
                                        <div class="flex items-center">
                                            <icon-menu-invoice class="group-hover:!text-primary shrink-0" />

                                            <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                                $t('invoice')
                                            }}</span>
                                        </div>
                                        <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'invoice' }">
                                            <icon-caret-down />
                                        </div>
                                    </button>
                                    <vue-collapsible :isOpen="activeDropdown === 'invoice'">
                                        <ul class="sub-menu text-gray-500">
                                            <li>
                                                <router-link to="/apps/invoice/list" @click="toggleMobileMenu">{{ $t('list') }}</router-link>
                                            </li>
                                            <li>
                                                <router-link to="/apps/invoice/preview" @click="toggleMobileMenu">{{ $t('preview') }}</router-link>
                                            </li>
                                            <li>
                                                <router-link to="/apps/invoice/add" @click="toggleMobileMenu">{{ $t('add') }}</router-link>
                                            </li>
                                            <li>
                                                <router-link to="/apps/invoice/edit" @click="toggleMobileMenu">{{ $t('edit') }}</router-link>
                                            </li>
                                        </ul>
                                    </vue-collapsible>
                                </li>

                                <li class="nav-item">
                                    <router-link to="/apps/calendar" class="group" @click="toggleMobileMenu">
                                        <div class="flex items-center">
                                            <icon-menu-calendar class="group-hover:!text-primary shrink-0" />

                                            <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                                $t('calendar')
                                            }}</span>
                                        </div>
                                    </router-link>
                                </li>
                            </ul>
                        </li>

                        <h2 class="py-3 px-7 flex items-center uppercase font-extrabold bg-white-light/30 dark:bg-dark dark:bg-opacity-[0.08] -mx-4 mb-1">
                            <icon-minus class="w-4 h-5 flex-none hidden" />
                            <span>{{ $t('user_interface') }}</span>
                        </h2>

                        <li class="menu nav-item">
                            <button
                                type="button"
                                class="nav-link group w-full"
                                :class="{ active: activeDropdown === 'components' }"
                                @click="activeDropdown === 'components' ? (activeDropdown = null) : (activeDropdown = 'components')"
                            >
                                <div class="flex items-center">
                                    <icon-menu-components class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                        $t('components')
                                    }}</span>
                                </div>
                                <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'components' }">
                                    <icon-caret-down />
                                </div>
                            </button>
                            <vue-collapsible :isOpen="activeDropdown === 'components'">
                                <ul class="sub-menu text-gray-500">
                                    <li>
                                        <router-link to="/components/tabs" @click="toggleMobileMenu">{{ $t('tabs') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/accordions" @click="toggleMobileMenu">{{ $t('accordions') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/modals" @click="toggleMobileMenu">{{ $t('modals') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/cards" @click="toggleMobileMenu">{{ $t('cards') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/carousel" @click="toggleMobileMenu">{{ $t('carousel') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/countdown" @click="toggleMobileMenu">{{ $t('countdown') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/counter" @click="toggleMobileMenu">{{ $t('counter') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/sweetalert" @click="toggleMobileMenu">{{ $t('sweet_alerts') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/timeline" @click="toggleMobileMenu">{{ $t('timeline') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/notifications" @click="toggleMobileMenu">{{ $t('notifications') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/media-object" @click="toggleMobileMenu">{{ $t('media_object') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/list-group" @click="toggleMobileMenu">{{ $t('list_group') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/pricing-table" @click="toggleMobileMenu">{{ $t('pricing_tables') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/components/lightbox" @click="toggleMobileMenu">{{ $t('lightbox') }}</router-link>
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>

                        <li class="menu nav-item">
                            <button
                                type="button"
                                class="nav-link group w-full"
                                :class="{ active: activeDropdown === 'elements' }"
                                @click="activeDropdown === 'elements' ? (activeDropdown = null) : (activeDropdown = 'elements')"
                            >
                                <div class="flex items-center">
                                    <icon-menu-elements class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{ $t('elements') }}</span>
                                </div>
                                <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'elements' }">
                                    <icon-caret-down />
                                </div>
                            </button>
                            <vue-collapsible :isOpen="activeDropdown === 'elements'">
                                <ul class="sub-menu text-gray-500">
                                    <li>
                                        <router-link to="/elements/alerts" @click="toggleMobileMenu">{{ $t('alerts') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/avatar" @click="toggleMobileMenu">{{ $t('avatar') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/badges" @click="toggleMobileMenu">{{ $t('badges') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/breadcrumbs" @click="toggleMobileMenu">{{ $t('breadcrumbs') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/buttons" @click="toggleMobileMenu">{{ $t('buttons') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/buttons-group" @click="toggleMobileMenu">{{ $t('button_groups') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/color-library" @click="toggleMobileMenu">{{ $t('color_library') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/dropdown" @click="toggleMobileMenu">{{ $t('dropdown') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/infobox" @click="toggleMobileMenu">{{ $t('infobox') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/jumbotron" @click="toggleMobileMenu">{{ $t('jumbotron') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/loader" @click="toggleMobileMenu">{{ $t('loader') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/pagination" @click="toggleMobileMenu">{{ $t('pagination') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/popovers" @click="toggleMobileMenu">{{ $t('popovers') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/progress-bar" @click="toggleMobileMenu">{{ $t('progress_bar') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/search" @click="toggleMobileMenu">{{ $t('search') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/tooltips" @click="toggleMobileMenu">{{ $t('tooltips') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/treeview" @click="toggleMobileMenu">{{ $t('treeview') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/elements/typography" @click="toggleMobileMenu">{{ $t('typography') }}</router-link>
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>

                        <li class="menu nav-item">
                            <router-link to="/charts" class="nav-link group" @click="toggleMobileMenu">
                                <div class="flex items-center">
                                    <icon-menu-charts class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{ $t('charts') }}</span>
                                </div>
                            </router-link>
                        </li>

                        <li class="menu nav-item">
                            <router-link to="/widgets" class="nav-link group" @click="toggleMobileMenu">
                                <div class="flex items-center">
                                    <icon-menu-widgets class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{ $t('widgets') }}</span>
                                </div>
                            </router-link>
                        </li>

                        <li class="menu nav-item">
                            <router-link to="/font-icons" class="nav-link group" @click="toggleMobileMenu">
                                <div class="flex items-center">
                                    <icon-menu-font-icons class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                        $t('font_icons')
                                    }}</span>
                                </div>
                            </router-link>
                        </li>

                        <li class="menu nav-item">
                            <router-link to="/dragndrop" class="nav-link group" @click="toggleMobileMenu">
                                <div class="flex items-center">
                                    <icon-menu-drag-and-drop class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                        $t('drag_and_drop')
                                    }}</span>
                                </div>
                            </router-link>
                        </li>

                        <h2 class="py-3 px-7 flex items-center uppercase font-extrabold bg-white-light/30 dark:bg-dark dark:bg-opacity-[0.08] -mx-4 mb-1">
                            <icon-minus class="w-4 h-5 flex-none hidden" />
                            <span>{{ $t('tables_and_forms') }}</span>
                        </h2>

                        <li class="menu nav-item">
                            <router-link to="/tables" class="nav-link group" @click="toggleMobileMenu">
                                <div class="flex items-center">
                                    <icon-menu-tables class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{ $t('tables') }}</span>
                                </div>
                            </router-link>
                        </li>

                        <li class="menu nav-item">
                            <button
                                type="button"
                                class="nav-link group w-full"
                                :class="{ active: activeDropdown === 'datatables' }"
                                @click="activeDropdown === 'datatables' ? (activeDropdown = null) : (activeDropdown = 'datatables')"
                            >
                                <div class="flex items-center">
                                    <icon-menu-datatables class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                        $t('datatables')
                                    }}</span>
                                </div>
                                <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'datatables' }">
                                    <icon-caret-down />
                                </div>
                            </button>
                            <vue-collapsible :isOpen="activeDropdown === 'datatables'">
                                <ul class="sub-menu text-gray-500">
                                    <li>
                                        <router-link to="/datatables/basic" @click="toggleMobileMenu">{{ $t('basic') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/advanced" @click="toggleMobileMenu">{{ $t('advanced') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/skin" @click="toggleMobileMenu">{{ $t('skin') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/order-sorting" @click="toggleMobileMenu">{{ $t('order_sorting') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/columns-filter" @click="toggleMobileMenu">{{ $t('columns_filter') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/multi-column" @click="toggleMobileMenu">{{ $t('multi_column') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/multiple-tables" @click="toggleMobileMenu">{{ $t('multiple_tables') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/alt-pagination" @click="toggleMobileMenu">{{ $t('alt_pagination') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/checkbox" @click="toggleMobileMenu">{{ $t('checkbox') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/range-search" @click="toggleMobileMenu">{{ $t('range_search') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/export" @click="toggleMobileMenu">{{ $t('export') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/sticky-header" @click="toggleMobileMenu">{{ $t('sticky_header') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/clone-header" @click="toggleMobileMenu">{{ $t('clone_header') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/datatables/column-chooser" @click="toggleMobileMenu">{{ $t('column_chooser') }}</router-link>
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>

                        <li class="menu nav-item">
                            <button
                                type="button"
                                class="nav-link group w-full"
                                :class="{ active: activeDropdown === 'forms' }"
                                @click="activeDropdown === 'forms' ? (activeDropdown = null) : (activeDropdown = 'forms')"
                            >
                                <div class="flex items-center">
                                    <icon-menu-forms class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{ $t('forms') }}</span>
                                </div>
                                <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'forms' }">
                                    <icon-caret-down />
                                </div>
                            </button>
                            <vue-collapsible :isOpen="activeDropdown === 'forms'">
                                <ul class="sub-menu text-gray-500">
                                    <li>
                                        <router-link to="/forms/basic" @click="toggleMobileMenu">{{ $t('basic') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/input-group" @click="toggleMobileMenu">{{ $t('input_group') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/layouts" @click="toggleMobileMenu">{{ $t('layouts') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/validation" @click="toggleMobileMenu">{{ $t('validation') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/input-mask" @click="toggleMobileMenu">{{ $t('input_mask') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/select2" @click="toggleMobileMenu">{{ $t('select2') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/touchspin" @click="toggleMobileMenu">{{ $t('touchspin') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/checkbox-radio" @click="toggleMobileMenu">{{ $t('checkbox_and_radio') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/switches" @click="toggleMobileMenu">{{ $t('switches') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/wizards" @click="toggleMobileMenu">{{ $t('wizards') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/file-upload" @click="toggleMobileMenu">{{ $t('file_upload') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/quill-editor" @click="toggleMobileMenu">{{ $t('quill_editor') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/markdown-editor" @click="toggleMobileMenu">{{ $t('markdown_editor') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/date-picker" @click="toggleMobileMenu">{{ $t('date_and_range_picker') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/forms/clipboard" @click="toggleMobileMenu">{{ $t('clipboard') }}</router-link>
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>

                        <h2 class="py-3 px-7 flex items-center uppercase font-extrabold bg-white-light/30 dark:bg-dark dark:bg-opacity-[0.08] -mx-4 mb-1">
                            <icon-minus class="w-4 h-5 flex-none hidden" />
                            <span>{{ $t('user_and_pages') }}</span>
                        </h2>

                        <li class="menu nav-item">
                            <button
                                type="button"
                                class="nav-link group w-full"
                                :class="{ active: activeDropdown === 'users' }"
                                @click="activeDropdown === 'users' ? (activeDropdown = null) : (activeDropdown = 'users')"
                            >
                                <div class="flex items-center">
                                    <icon-menu-users class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{ $t('users') }}</span>
                                </div>
                                <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'users' }">
                                    <icon-caret-down />
                                </div>
                            </button>
                            <vue-collapsible :isOpen="activeDropdown === 'users'">
                                <ul class="sub-menu text-gray-500">
                                    <li>
                                        <router-link to="/users/profile" @click="toggleMobileMenu">{{ $t('profile') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/users/user-account-settings" @click="toggleMobileMenu">{{ $t('account_settings') }}</router-link>
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>

                        <li class="menu nav-item">
                            <button
                                type="button"
                                class="nav-link group w-full"
                                :class="{ active: activeDropdown === 'pages' }"
                                @click="activeDropdown === 'pages' ? (activeDropdown = null) : (activeDropdown = 'pages')"
                            >
                                <div class="flex items-center">
                                    <icon-menu-pages class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{ $t('pages') }}</span>
                                </div>
                                <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'pages' }">
                                    <icon-caret-down />
                                </div>
                            </button>
                            <vue-collapsible :isOpen="activeDropdown === 'pages'">
                                <ul class="sub-menu text-gray-500">
                                    <li>
                                        <router-link to="/pages/knowledge-base" @click="toggleMobileMenu">{{ $t('knowledge_base') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/pages/contact-us-boxed" target="_blank">{{ $t('contact_us_boxed') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/pages/contact-us-cover" target="_blank">{{ $t('contact_us_cover') }}</router-link>
                                    </li>
                                    <li>
                                        <router-link to="/pages/faq" @click="toggleMobileMenu">{{ $t('faq') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/pages/coming-soon-boxed" target="_blank">{{ $t('coming_soon_boxed') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/pages/coming-soon-cover" target="_blank">{{ $t('coming_soon_cover') }}</router-link>
                                    </li>
                                    <li class="menu nav-item">
                                        <button
                                            type="button"
                                            class="w-full before:bg-gray-300 before:w-[5px] before:h-[5px] before:rounded ltr:before:mr-2 rtl:before:ml-2 dark:text-[#888ea8] hover:bg-gray-100 dark:hover:bg-gray-900"
                                            @click="subActive === 'error' ? (subActive = null) : (subActive = 'error')"
                                        >
                                            {{ $t('error') }}
                                            <div class="ltr:ml-auto rtl:mr-auto" :class="{ 'rtl:rotate-90 -rotate-90': subActive !== 'error' }">
                                                <icon-carets-down :fill="true" class="w-4 h-4" />
                                            </div>
                                        </button>

                                        <vue-collapsible :isOpen="subActive === 'error'">
                                            <ul :unmount="false" class="sub-menu text-gray-500">
                                                <li @click="toggleMobileMenu">
                                                    <router-link to="/pages/error404" target="_blank">{{ $t('404') }}</router-link>
                                                </li>
                                                <li @click="toggleMobileMenu">
                                                    <router-link to="/pages/error500" target="_blank">{{ $t('500') }}</router-link>
                                                </li>
                                                <li @click="toggleMobileMenu">
                                                    <router-link to="/pages/error503" target="_blank">{{ $t('503') }}</router-link>
                                                </li>
                                            </ul>
                                        </vue-collapsible>
                                    </li>
                                    <li>
                                        <router-link to="/pages/maintenence" target="_blank">{{ $t('maintenence') }}</router-link>
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>

                        <li class="menu nav-item">
                            <button
                                type="button"
                                class="nav-link group w-full"
                                :class="{ active: activeDropdown === 'authentication' }"
                                @click="activeDropdown === 'authentication' ? (activeDropdown = null) : (activeDropdown = 'authentication')"
                            >
                                <div class="flex items-center">
                                    <icon-menu-authentication class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                        $t('authentication')
                                    }}</span>
                                </div>
                                <div :class="{ 'rtl:rotate-90 -rotate-90': activeDropdown !== 'authentication' }">
                                    <icon-caret-down />
                                </div>
                            </button>
                            <vue-collapsible :isOpen="activeDropdown === 'authentication'">
                                <ul class="sub-menu text-gray-500">
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/auth/boxed-signin" target="_blank">{{ $t('login_boxed') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/auth/boxed-signup" target="_blank">{{ $t('register_boxed') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/auth/boxed-lockscreen" target="_blank">{{ $t('unlock_boxed') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/auth/boxed-password-reset" target="_blank">{{ $t('recover_id_boxed') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/auth/cover-login" target="_blank">{{ $t('login_cover') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/auth/cover-register" target="_blank">{{ $t('register_cover') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/auth/cover-lockscreen" target="_blank">{{ $t('unlock_cover') }}</router-link>
                                    </li>
                                    <li @click="toggleMobileMenu">
                                        <router-link to="/auth/cover-password-reset" target="_blank">{{ $t('recover_id_cover') }}</router-link>
                                    </li>
                                </ul>
                            </vue-collapsible>
                        </li>

                        <h2 class="py-3 px-7 flex items-center uppercase font-extrabold bg-white-light/30 dark:bg-dark dark:bg-opacity-[0.08] -mx-4 mb-1">
                            <icon-minus class="w-4 h-5 flex-none hidden" />
                            <span>{{ $t('supports') }}</span>
                        </h2>

                        <li class="menu nav-item">
                            <a href="https://vristo.sbthemes.com" target="_blank" class="nav-link group">
                                <div class="flex items-center">
                                    <icon-menu-documentation class="group-hover:!text-primary shrink-0" />

                                    <span class="ltr:pl-3 rtl:pr-3 text-black dark:text-[#506690] dark:group-hover:text-white-dark">{{
                                        $t('documentation')
                                    }}</span>
                                </div>
                            </a>
                        </li>
                    </ul>
                </perfect-scrollbar>
            </div>
        </nav>
    </div>
</template>

<script lang="ts" setup>
    import { ref, onMounted } from 'vue';

    import { useAppStore } from '@/stores/index';
    import VueCollapsible from 'vue-height-collapsible/vue3';

    import IconCaretsDown from '@/components/icon/icon-carets-down.vue';
    import IconMenuDashboard from '@/components/icon/menu/icon-menu-dashboard.vue';
    import IconMinus from '@/components/icon/icon-minus.vue';
    import IconMenuChat from '@/components/icon/menu/icon-menu-chat.vue';
    import IconMenuMailbox from '@/components/icon/menu/icon-menu-mailbox.vue';
    import IconMenuTodo from '@/components/icon/menu/icon-menu-todo.vue';
    import IconMenuNotes from '@/components/icon/menu/icon-menu-notes.vue';
    import IconMenuScrumboard from '@/components/icon/menu/icon-menu-scrumboard.vue';
    import IconMenuContacts from '@/components/icon/menu/icon-menu-contacts.vue';
    import IconMenuInvoice from '@/components/icon/menu/icon-menu-invoice.vue';
    import IconCaretDown from '@/components/icon/icon-caret-down.vue';
    import IconMenuCalendar from '@/components/icon/menu/icon-menu-calendar.vue';
    import IconMenuComponents from '@/components/icon/menu/icon-menu-components.vue';
    import IconMenuElements from '@/components/icon/menu/icon-menu-elements.vue';
    import IconMenuCharts from '@/components/icon/menu/icon-menu-charts.vue';
    import IconMenuWidgets from '@/components/icon/menu/icon-menu-widgets.vue';
    import IconMenuFontIcons from '@/components/icon/menu/icon-menu-font-icons.vue';
    import IconMenuDragAndDrop from '@/components/icon/menu/icon-menu-drag-and-drop.vue';
    import IconMenuTables from '@/components/icon/menu/icon-menu-tables.vue';
    import IconMenuDatatables from '@/components/icon/menu/icon-menu-datatables.vue';
    import IconMenuForms from '@/components/icon/menu/icon-menu-forms.vue';
    import IconMenuUsers from '@/components/icon/menu/icon-menu-users.vue';
    import IconMenuPages from '@/components/icon/menu/icon-menu-pages.vue';
    import IconMenuAuthentication from '@/components/icon/menu/icon-menu-authentication.vue';
    import IconMenuDocumentation from '@/components/icon/menu/icon-menu-documentation.vue';

    const store = useAppStore();
    const activeDropdown: any = ref('');
    const subActive: any = ref('');

    onMounted(() => {
        const selector = document.querySelector('.sidebar ul a[href="' + window.location.pathname + '"]');
        if (selector) {
            selector.classList.add('active');
            const ul: any = selector.closest('ul.sub-menu');
            if (ul) {
                let ele: any = ul.closest('li.menu').querySelectorAll('.nav-link') || [];
                if (ele.length) {
                    ele = ele[0];
                    setTimeout(() => {
                        ele.click();
                    });
                }
            }
        }
    });

    const toggleMobileMenu = () => {
        if (window.innerWidth < 1024) {
            store.toggleSidebar();
        }
    };
</script>
