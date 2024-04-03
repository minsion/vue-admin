<template>
    <div>
        <ul class="flex space-x-2 rtl:space-x-reverse">
            <li>
                <a href="javascript:;" class="text-primary hover:underline">Components</a>
            </li>
            <li class="before:content-['/'] ltr:before:mr-2 rtl:before:ml-2">
                <span>Tabs</span>
            </li>
        </ul>
        <div class="pt-5 space-y-8">
            <div class="panel p-3 flex items-center text-primary overflow-x-auto whitespace-nowrap">
                <div class="ring-2 ring-primary/30 rounded-full bg-primary text-white p-1.5 ltr:mr-3 rtl:ml-3">
                    <icon-bell />
                </div>
                <span class="ltr:mr-3 rtl:ml-3">Documentation: </span
                ><a href="https://headlessui.com/vue/tabs" target="_blank" class="block hover:underline">https://headlessui.com/vue/tabs</a>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                <!-- Simple Tabs -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Simple Tabs</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code1')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap mt-3 border-b border-white-light dark:border-[#191e3a]">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:text-primary dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white  text-primary dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Home</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:text-primary dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white text-primary dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Profile</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:text-primary dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white text-primary dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Contact</a
                                >
                            </Tab>
                            <Tab as="template" disabled>
                                <a href="javascript:;" class="p-3.5 py-2 -mb-[1px] block pointer-events-none text-white-light dark:text-dark">Disabled</a>
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>Disabled</TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code1')">
                        <highlight>
                            <pre>
&lt;!-- simple tabs --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
  &lt;TabList class=&quot;flex flex-wrap mt-3 border-b border-white-light dark:border-[#191e3a]&quot;&gt;
    &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
      &lt;a
        href=&quot;javascript:;&quot;
        class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:text-primary dark:hover:border-b-black !outline-none transition duration-300&quot;
        :class=&quot;{ '!border-white-light !border-b-white  text-primary dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
        &gt;Home&lt;/a
      &gt;
    &lt;/Tab&gt;
    &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
      &lt;a
        href=&quot;javascript:;&quot;
        class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:text-primary dark:hover:border-b-black !outline-none transition duration-300&quot;
        :class=&quot;{ '!border-white-light !border-b-white text-primary dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
        &gt;Profile&lt;/a
      &gt;
    &lt;/Tab&gt;
    &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
      &lt;a
        href=&quot;javascript:;&quot;
        class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:text-primary dark:hover:border-b-black !outline-none transition duration-300&quot;
        :class=&quot;{ '!border-white-light !border-b-white text-primary dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
        &gt;Contact&lt;/a
      &gt;
    &lt;/Tab&gt;
    &lt;Tab as=&quot;template&quot; disabled&gt;
      &lt;a href=&quot;javascript:;&quot; class=&quot;p-3.5 py-2 -mb-[1px] block pointer-events-none text-white-light dark:text-dark&quot;&gt;Disabled&lt;/a&gt;
    &lt;/Tab&gt;
  &lt;/TabList&gt;
  &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
    &lt;TabPanel&gt;
      &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
      &lt;p class=&quot;mb-4&quot;&gt;
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
        ullamco laboris nisi ut aliquip ex ea commodo consequat.
      &lt;/p&gt;
      &lt;p&gt;
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
        ullamco laboris nisi ut aliquip ex ea commodo consequat.
      &lt;/p&gt;
    &lt;/TabPanel&gt;
    &lt;TabPanel&gt;
      &lt;div class=&quot;flex items-start&quot;&gt;
        &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
          &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
        &lt;/div&gt;
        &lt;div class=&quot;flex-auto&quot;&gt;
          &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
          &lt;p class=&quot;text-white-dark&quot;&gt;
            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum
            nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
          &lt;/p&gt;
        &lt;/div&gt;
      &lt;/div&gt;
    &lt;/TabPanel&gt;
    &lt;TabPanel&gt;
      &lt;p&gt;
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
        ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
        occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      &lt;/p&gt;
    &lt;/TabPanel&gt;
    &lt;TabPanel&gt;Disabled&lt;/TabPanel&gt;
  &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Simple Pills -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Simple Pills</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code2')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap mt-3">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] ltr:mr-2 rtl:ml-2 block rounded hover:bg-primary hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-primary text-white': selected }"
                                    >Home</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] ltr:mr-2 rtl:ml-2 block rounded hover:bg-primary hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-primary text-white': selected }"
                                    >Profile</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] ltr:mr-2 rtl:ml-2 block rounded hover:bg-primary hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-primary text-white': selected }"
                                    >Contact</a
                                >
                            </Tab>
                            <Tab as="template" disabled>
                                <a href="javascript:;" class="p-3.5 py-2 -mb-[1px] block rounded pointer-events-none text-white-light dark:text-dark"
                                    >Disabled</a
                                >
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>Disabled</TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code2')">
                        <highlight>
                            <pre>
&lt;!-- simple pills --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
  &lt;TabList class=&quot;flex flex-wrap mt-3&quot;&gt;
    &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
      &lt;a
        href=&quot;javascript:;&quot;
        class=&quot;p-3.5 py-2 -mb-[1px] ltr:mr-2 rtl:ml-2 block rounded hover:bg-primary hover:text-white !outline-none transition duration-300&quot;
        :class=&quot;{ 'bg-primary text-white': selected === 'home' }&quot;
        &gt;Home&lt;/a
      &gt;
    &lt;/Tab&gt;
    &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
      &lt;a
        href=&quot;javascript:;&quot;
        class=&quot;p-3.5 py-2 -mb-[1px] ltr:mr-2 rtl:ml-2 block rounded hover:bg-primary hover:text-white !outline-none transition duration-300&quot;
        :class=&quot;{ 'bg-primary text-white': selected === 'profile' }&quot;
        &gt;Profile&lt;/a
      &gt;
    &lt;/Tab&gt;
    &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
      &lt;a
        href=&quot;javascript:;&quot;
        class=&quot;p-3.5 py-2 -mb-[1px] ltr:mr-2 rtl:ml-2 block rounded hover:bg-primary hover:text-white !outline-none transition duration-300&quot;
        :class=&quot;{ 'bg-primary text-white': selected === 'contact' }&quot;
        &gt;Contact&lt;/a
      &gt;
    &lt;/Tab&gt;
    &lt;Tab as=&quot;template&quot; disabled&gt;
      &lt;a href=&quot;javascript:;&quot; class=&quot;p-3.5 py-2 -mb-[1px] block rounded pointer-events-none text-white-light dark:text-dark&quot;&gt;Disabled&lt;/a&gt;
    &lt;/Tab&gt;
  &lt;/TabList&gt;
  &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
    &lt;TabPanel&gt;
      &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
      &lt;p class=&quot;mb-4&quot;&gt;
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
        ullamco laboris nisi ut aliquip ex ea commodo consequat.
      &lt;/p&gt;
      &lt;p&gt;
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
        ullamco laboris nisi ut aliquip ex ea commodo consequat.
      &lt;/p&gt;
    &lt;/TabPanel&gt;
    &lt;TabPanel&gt;
      &lt;div class=&quot;flex items-start&quot;&gt;
        &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
          &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
        &lt;/div&gt;
        &lt;div class=&quot;flex-auto&quot;&gt;
          &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
          &lt;p class=&quot;text-white-dark&quot;&gt;
            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum
            nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
          &lt;/p&gt;
        &lt;/div&gt;
      &lt;/div&gt;
    &lt;/TabPanel&gt;
    &lt;TabPanel&gt;
      &lt;p&gt;
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation
        ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
        occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      &lt;/p&gt;
    &lt;/TabPanel&gt;
    &lt;TabPanel&gt;Disabled&lt;/TabPanel&gt;
  &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Icon Tabs -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Icon Tabs</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code3')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap mt-3 border-b border-white-light dark:border-[#191e3a]">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                >
                                    <icon-home class="ltr:mr-2 rtl:ml-2" />

                                    Home
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                >
                                    <icon-user class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Profile
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                >
                                    <icon-phone class="ltr:mr-2 rtl:ml-2" />
                                    Contact
                                </a>
                            </Tab>
                            <Tab as="template" disabled>
                                <a href="javascript:;" class="p-3.5 py-2 -mb-[1px] flex items-center pointer-events-none text-white-light dark:text-dark">
                                    <icon-info-circle class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Disabled
                                </a>
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>Disabled</TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code3')">
                        <highlight>
                            <pre>
&lt;!-- icon tabs --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap mt-3 border-b border-white-light dark:border-[#191e3a]&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Home
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Profile
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Contact
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; disabled&gt;
            &lt;a href=&quot;javascript:;&quot; class=&quot;p-3.5 py-2 -mb-[1px] flex items-center pointer-events-none text-white-light dark:text-dark&quot;&gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Disabled
            &lt;/a&gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;Disabled&lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Icon Pills -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Icon Pills</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code4')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap mt-3 gap-2">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center rounded hover:bg-warning hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-warning text-white': selected }"
                                >
                                    <icon-home class="ltr:mr-2 rtl:ml-2" />
                                    Home
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center rounded hover:bg-warning hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-warning text-white': selected }"
                                >
                                    <icon-user class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Profile
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center rounded hover:bg-warning hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-warning text-white': selected }"
                                >
                                    <icon-phone class="ltr:mr-2 rtl:ml-2" />
                                    Contact
                                </a>
                            </Tab>
                            <Tab as="template" disabled>
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center rounded pointer-events-none text-white-light dark:text-dark"
                                >
                                    <icon-info-circle class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Disabled
                                </a>
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>Disabled</TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code4')">
                        <highlight>
                            <pre>
&lt;!-- icon pills --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap mt-3 gap-2&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center rounded hover:bg-warning hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-warning text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Home
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center rounded hover:bg-warning hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-warning text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Profile
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center rounded hover:bg-warning hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-warning text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Contact
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; disabled&gt;
            &lt;a href=&quot;javascript:;&quot; class=&quot;p-3.5 py-2 -mb-[1px] flex items-center rounded pointer-events-none text-white-light dark:text-dark&quot;&gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Disabled
            &lt;/a&gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;Disabled&lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Vertical Border -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Vertical Bordered</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code5')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5 flex flex-col sm:flex-row">
                        <div class="mx-10 mb-5 sm:mb-0">
                            <TabList class="w-24 m-auto text-center">
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-3.5 py-2 -mb-[1px] block border border-white-light dark:border-[#191e3a] hover:bg-success hover:text-white !outline-none transition duration-300"
                                        :class="{ 'bg-success text-white': selected }"
                                        >Home</a
                                    >
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-3.5 py-2 -mb-[1px] block border border-white-light dark:border-[#191e3a] hover:bg-success hover:text-white !outline-none transition duration-300"
                                        :class="{ 'bg-success text-white': selected }"
                                        >Profile</a
                                    >
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-3.5 py-2 -mb-[1px] block border border-white-light dark:border-[#191e3a] hover:bg-success hover:text-white !outline-none transition duration-300"
                                        :class="{ 'bg-success text-white': selected }"
                                        >Messages</a
                                    >
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-3.5 py-2 -mb-[1px] block border border-white-light dark:border-[#191e3a] hover:bg-success hover:text-white !outline-none transition duration-300"
                                        :class="{ 'bg-success text-white': selected }"
                                        >Settings</a
                                    >
                                </Tab>
                            </TabList>
                        </div>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <blockquote
                                    class="text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]"
                                >
                                    <div class="flex items-start">
                                        <p class="not-italic text-[#515365] text-sm dark:text-white-dark m-0">
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                                        </p>
                                    </div>
                                </blockquote>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code5')">
                        <highlight>
                            <pre>
&lt;!-- vertical border --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5 flex flex-col sm:flex-row&quot;&gt;
    &lt;div class=&quot;mx-10 mb-5 sm:mb-0&quot;&gt;
        &lt;TabList class=&quot;w-24 m-auto text-center&quot;&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-3.5 py-2 -mb-[1px] block border border-white-light dark:border-[#191e3a] hover:bg-success hover:text-white !outline-none transition duration-300&quot;
                    :class=&quot;{ 'bg-success text-white': selected }&quot;
                    &gt;Home&lt;/a
                &gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-3.5 py-2 -mb-[1px] block border border-white-light dark:border-[#191e3a] hover:bg-success hover:text-white !outline-none transition duration-300&quot;
                    :class=&quot;{ 'bg-success text-white': selected }&quot;
                    &gt;Profile&lt;/a
                &gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-3.5 py-2 -mb-[1px] block border border-white-light dark:border-[#191e3a] hover:bg-success hover:text-white !outline-none transition duration-300&quot;
                    :class=&quot;{ 'bg-success text-white': selected }&quot;
                    &gt;Messages&lt;/a
                &gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-3.5 py-2 -mb-[1px] block border border-white-light dark:border-[#191e3a] hover:bg-success hover:text-white !outline-none transition duration-300&quot;
                    :class=&quot;{ 'bg-success text-white': selected }&quot;
                    &gt;Settings&lt;/a
                &gt;
            &lt;/Tab&gt;
        &lt;/TabList&gt;
    &lt;/div&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;blockquote
                class=&quot;text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]&quot;
            &gt;
                &lt;div class=&quot;flex items-start&quot;&gt;
                    &lt;p class=&quot;not-italic text-[#515365] text-sm dark:text-white-dark m-0&quot;&gt;
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/blockquote&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Border Tabs -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Border Tabs</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code6')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap mt-3 border-b border-white-light dark:border-[#191e3a]">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                >
                                    <icon-home class="ltr:mr-2 rtl:ml-2" />
                                    Home
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                >
                                    <icon-user class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Profile
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                >
                                    <icon-phone class="ltr:mr-2 rtl:ml-2" />
                                    Contact
                                </a>
                            </Tab>
                        </TabList>
                        <TabPanels class="p-4 flex-1 text-sm border border-white-light border-t-0 dark:border-[#191e3a]">
                            <TabPanel class="active">
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code6')">
                        <highlight>
                            <pre>
&lt;!-- border tabs --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap mt-3 border-b border-white-light dark:border-[#191e3a]&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Home
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Profile
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] flex items-center border border-transparent hover:text-danger !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white text-danger dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Contact
            &lt;/a&gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;p-4 flex-1 text-sm border border-white-light border-t-0 dark:border-[#191e3a]&quot;&gt;
        &lt;TabPanel class=&quot;active&quot;&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Border Top -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Border Top</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code7')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap mt-3 mb-5">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-7 py-3 flex items-center bg-[#f6f7f8] dark:bg-transparent border-transparent border-t-2 dark:hover:bg-[#191e3a] hover:border-secondary hover:text-secondary !outline-none transition duration-300"
                                    :class="{ '!border-secondary text-secondary dark:bg-[#191e3a]': selected }"
                                >
                                    <icon-home class="ltr:mr-2 rtl:ml-2" />
                                    Home
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-7 py-3 flex items-center bg-[#f6f7f8] dark:bg-transparent dark:hover:bg-[#191e3a] border-transparent border-t-2 hover:border-secondary hover:text-secondary !outline-none transition duration-300"
                                    :class="{ '!border-secondary text-secondary dark:bg-[#191e3a]': selected }"
                                >
                                    <icon-user class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Profile
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-7 py-3 flex items-center bg-[#f6f7f8] dark:bg-transparent dark:hover:bg-[#191e3a] border-transparent border-t-2 hover:border-secondary hover:text-secondary !outline-none transition duration-300"
                                    :class="{ '!border-secondary text-secondary dark:bg-[#191e3a]': selected }"
                                >
                                    <icon-phone class="ltr:mr-2 rtl:ml-2" />
                                    Contact
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-7 py-3 flex items-center bg-[#f6f7f8] dark:bg-transparent dark:hover:bg-[#191e3a] border-transparent border-t-2 hover:border-secondary hover:text-secondary !outline-none transition duration-300"
                                    :class="{ '!border-secondary text-secondary dark:bg-[#191e3a]': selected }"
                                >
                                    <icon-settings class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Settings
                                </a>
                            </Tab>
                        </TabList>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <blockquote
                                    class="text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]"
                                >
                                    <div class="flex items-start">
                                        <p class="not-italic text-[#515365] text-sm dark:text-white-dark m-0">
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                                        </p>
                                    </div>
                                </blockquote>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code7')">
                        <highlight>
                            <pre>
&lt;!-- border top --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap mt-3 mb-5&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-7 py-3 flex items-center bg-[#f6f7f8] dark:bg-transparent border-transparent border-t-2 dark:hover:bg-[#191e3a] hover:border-secondary hover:text-secondary !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-secondary text-secondary dark:bg-[#191e3a]': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Home
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-7 py-3 flex items-center bg-[#f6f7f8] dark:bg-transparent dark:hover:bg-[#191e3a] border-transparent border-t-2 hover:border-secondary hover:text-secondary !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-secondary text-secondary dark:bg-[#191e3a]': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Profile
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-7 py-3 flex items-center bg-[#f6f7f8] dark:bg-transparent dark:hover:bg-[#191e3a] border-transparent border-t-2 hover:border-secondary hover:text-secondary !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-secondary text-secondary dark:bg-[#191e3a]': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Contact
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-7 py-3 flex items-center bg-[#f6f7f8] dark:bg-transparent dark:hover:bg-[#191e3a] border-transparent border-t-2 hover:border-secondary hover:text-secondary !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-secondary text-secondary dark:bg-[#191e3a]': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Settings
            &lt;/a&gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;blockquote
                class=&quot;text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]&quot;
            &gt;
                &lt;div class=&quot;flex items-start&quot;&gt;
                    &lt;p class=&quot;not-italic text-[#515365] text-sm dark:text-white-dark m-0&quot;&gt;
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/blockquote&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Line -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Line</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code8')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap mt-3 mb-5 border-b border-white-light dark:border-[#191e3a]">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-5 py-3 -mb-[1px] flex items-center hover:border-b border-transparent hover:!border-secondary hover:text-secondary !outline-none transition duration-300"
                                    :class="{ 'border-b !border-secondary text-secondary': selected }"
                                >
                                    <icon-home class="ltr:mr-2 rtl:ml-2" />
                                    Home
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-5 py-3 -mb-[1px] flex items-center hover:border-b border-transparent hover:!border-secondary hover:text-secondary !outline-none transition duration-300"
                                    :class="{ 'border-b !border-secondary text-secondary': selected }"
                                >
                                    <icon-user class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Profile
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-5 py-3 -mb-[1px] flex items-center hover:border-b border-transparent hover:!border-secondary hover:text-secondary !outline-none transition duration-300"
                                    :class="{ 'border-b !border-secondary text-secondary': selected }"
                                >
                                    <icon-phone class="ltr:mr-2 rtl:ml-2" />
                                    Contact
                                </a>
                            </Tab>
                        </TabList>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code8')">
                        <highlight>
                            <pre>
&lt;!-- line --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap mt-3 mb-5 border-b border-white-light dark:border-[#191e3a]&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-5 py-3 -mb-[1px] flex items-center hover:border-b border-transparent hover:!border-secondary hover:text-secondary !outline-none transition duration-300&quot;
                :class=&quot;{ 'border-b !border-secondary text-secondary': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Home
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-5 py-3 -mb-[1px] flex items-center hover:border-b border-transparent hover:!border-secondary hover:text-secondary !outline-none transition duration-300&quot;
                :class=&quot;{ 'border-b !border-secondary text-secondary': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Profile
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-5 py-3 -mb-[1px] flex items-center hover:border-b border-transparent hover:!border-secondary hover:text-secondary !outline-none transition duration-300&quot;
                :class=&quot;{ 'border-b !border-secondary text-secondary': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Contact
            &lt;/a&gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Animated line -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Animated Line</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code9')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap mt-3 mb-5 border-b border-white-light dark:border-[#191e3a]">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-5 py-3 -mb-[1px] flex items-center relative before:transition-all before:duration-700 before:absolute hover:text-secondary before:bottom-0 before:w-0 before:left-0 before:right-0 before:m-auto before:h-[1px] before:bg-secondary hover:before:w-full !outline-none transition duration-300"
                                    :class="{ 'before:!w-full text-secondary': selected }"
                                >
                                    <icon-home class="ltr:mr-2 rtl:ml-2" />
                                    Home
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-5 py-3 -mb-[1px] flex items-center relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-0 before:bottom-0 before:left-0 before:right-0 before:m-auto before:h-[1px] before:bg-secondary hover:before:w-full !outline-none transition duration-300"
                                    :class="{ 'before:!w-full text-secondary': selected }"
                                >
                                    <icon-user class="w-5 h-5 ltr:mr-2 rtl:ml-2" />
                                    Profile
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-5 py-3 -mb-[1px] flex items-center relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-0 before:bottom-0 before:left-0 before:right-0 before:m-auto before:h-[1px] before:bg-secondary hover:before:w-full !outline-none transition duration-300"
                                    :class="{ 'before:!w-full text-secondary': selected }"
                                >
                                    <icon-phone class="ltr:mr-2 rtl:ml-2" />
                                    Contact
                                </a>
                            </Tab>
                        </TabList>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover /"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code9')">
                        <highlight>
                            <pre>
&lt;!-- animated line --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap mt-3 mb-5 border-b border-white-light dark:border-[#191e3a]&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-5 py-3 -mb-[1px] flex items-center relative before:transition-all before:duration-700 before:absolute hover:text-secondary before:bottom-0 before:w-0 before:left-0 before:right-0 before:m-auto before:h-[1px] before:bg-secondary hover:before:w-full !outline-none transition duration-300&quot;
                :class=&quot;{ 'before:!w-full text-secondary': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Home
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-5 py-3 -mb-[1px] flex items-center relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-0 before:bottom-0 before:left-0 before:right-0 before:m-auto before:h-[1px] before:bg-secondary hover:before:w-full !outline-none transition duration-300&quot;
                :class=&quot;{ 'before:!w-full text-secondary': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Profile
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-5 py-3 -mb-[1px] flex items-center relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-0 before:bottom-0 before:left-0 before:right-0 before:m-auto before:h-[1px] before:bg-secondary hover:before:w-full !outline-none transition duration-300&quot;
                :class=&quot;{ 'before:!w-full text-secondary': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Contact
            &lt;/a&gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover /&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Vertical line tabs -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Vertical Line Tab</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code10')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5 flex flex-col sm:flex-row">
                        <div class="mx-10 mb-5 sm:mb-0">
                            <TabList class="w-24 m-auto text-center font-semibold">
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-3.5 py-4 -mb-[1px] block ltr:border-r rtl:border-l border-white-light dark:border-[#191e3a] relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-[1px] before:bottom-0 before:top-0 ltr:before:-right-[1px] rtl:before:-left-[1px] before:m-auto before:h-0 before:bg-secondary hover:before:h-[80%] !outline-none transition duration-300"
                                        :class="{ 'text-secondary before:!h-[80%]': selected }"
                                        >Home</a
                                    >
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-3.5 py-4 -mb-[1px] block ltr:border-r rtl:border-l border-white-light dark:border-[#191e3a] relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-[1px] before:bottom-0 before:top-0 ltr:before:-right-[1px] rtl:before:-left-[1px] before:m-auto before:h-0 before:bg-secondary hover:before:h-[80%] !outline-none transition duration-300"
                                        :class="{ 'text-secondary before:!h-[80%]': selected }"
                                        >Profile</a
                                    >
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-3.5 py-4 -mb-[1px] block ltr:border-r rtl:border-l border-white-light dark:border-[#191e3a] relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-[1px] before:bottom-0 before:top-0 ltr:before:-right-[1px] rtl:before:-left-[1px] before:m-auto before:h-0 before:bg-secondary hover:before:h-[80%] !outline-none transition duration-300"
                                        :class="{ 'text-secondary before:!h-[80%]': selected }"
                                        >Messages</a
                                    >
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-3.5 py-4 -mb-[1px] block ltr:border-r rtl:border-l border-white-light dark:border-[#191e3a] relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-[1px] before:bottom-0 before:top-0 ltr:before:-right-[1px] rtl:before:-left-[1px] before:m-auto before:h-0 before:bg-secondary hover:before:h-[80%] !outline-none transition duration-300"
                                        :class="{ 'text-secondary before:!h-[80%]': selected }"
                                        >Settings</a
                                    >
                                </Tab>
                            </TabList>
                        </div>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <blockquote
                                    class="text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]"
                                >
                                    <div class="flex items-start">
                                        <p class="not-italic text-[#515365] text-sm dark:text-white-dark m-0">
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                                        </p>
                                    </div>
                                </blockquote>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code10')">
                        <highlight>
                            <pre>
&lt;!-- Vertical line tabs --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5 flex flex-col sm:flex-row&quot;&gt;
    &lt;div class=&quot;mx-10 mb-5 sm:mb-0&quot;&gt;
        &lt;TabList class=&quot;w-24 m-auto text-center font-semibold&quot;&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-3.5 py-4 -mb-[1px] block ltr:border-r rtl:border-l border-white-light dark:border-[#191e3a] relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-[1px] before:bottom-0 before:top-0 ltr:before:-right-[1px] rtl:before:-left-[1px] before:m-auto before:h-0 before:bg-secondary hover:before:h-[80%] !outline-none transition duration-300&quot;
                    :class=&quot;{ 'text-secondary before:!h-[80%]': selected }&quot;
                    &gt;Home&lt;/a
                &gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-3.5 py-4 -mb-[1px] block ltr:border-r rtl:border-l border-white-light dark:border-[#191e3a] relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-[1px] before:bottom-0 before:top-0 ltr:before:-right-[1px] rtl:before:-left-[1px] before:m-auto before:h-0 before:bg-secondary hover:before:h-[80%] !outline-none transition duration-300&quot;
                    :class=&quot;{ 'text-secondary before:!h-[80%]': selected }&quot;
                    &gt;Profile&lt;/a
                &gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-3.5 py-4 -mb-[1px] block ltr:border-r rtl:border-l border-white-light dark:border-[#191e3a] relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-[1px] before:bottom-0 before:top-0 ltr:before:-right-[1px] rtl:before:-left-[1px] before:m-auto before:h-0 before:bg-secondary hover:before:h-[80%] !outline-none transition duration-300&quot;
                    :class=&quot;{ 'text-secondary before:!h-[80%]': selected }&quot;
                    &gt;Messages&lt;/a
                &gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-3.5 py-4 -mb-[1px] block ltr:border-r rtl:border-l border-white-light dark:border-[#191e3a] relative before:transition-all before:duration-700 hover:text-secondary before:absolute before:w-[1px] before:bottom-0 before:top-0 ltr:before:-right-[1px] rtl:before:-left-[1px] before:m-auto before:h-0 before:bg-secondary hover:before:h-[80%] !outline-none transition duration-300&quot;
                    :class=&quot;{ 'text-secondary before:!h-[80%]': selected }&quot;
                    &gt;Settings&lt;/a
                &gt;
            &lt;/Tab&gt;
        &lt;/TabList&gt;
    &lt;/div&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;blockquote
                class=&quot;text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]&quot;
            &gt;
                &lt;div class=&quot;flex items-start&quot;&gt;
                    &lt;p class=&quot;not-italic text-[#515365] text-sm dark:text-white-dark m-0&quot;&gt;
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/blockquote&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Justify tabs -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Justify Tabs</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code11')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap justify-between mt-3 border-b border-white-light dark:border-[#191e3a] text-center">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="flex-auto p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Home</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="flex-auto p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Profile</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="flex-auto p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ '!border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Contact</a
                                >
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code11')">
                        <highlight>
                            <pre>
&lt;!-- justify tabs --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap justify-between mt-3 border-b border-white-light dark:border-[#191e3a] text-center&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;flex-auto p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Home&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;flex-auto p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Profile&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;flex-auto p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ '!border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Contact&lt;/a
            &gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Justify Pills -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Justify Pills</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code12')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap justify-between mt-3 space-x-2 rtl:space-x-reverse text-center">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="flex-auto p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Home</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="flex-auto p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Profile</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="flex-auto p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Contact</a
                                >
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code12')">
                        <highlight>
                            <pre>
&lt;!-- justify pills --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap justify-between mt-3 space-x-2 rtl:space-x-reverse text-center&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;flex-auto p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Home&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;flex-auto p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Profile&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;flex-auto p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Contact&lt;/a
            &gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Justify Center Tabs -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Justify Center Tabs</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code13')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap justify-center mt-3 border-b border-white-light dark:border-[#191e3a]">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Home</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Profile</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Contact</a
                                >
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code13')">
                        <highlight>
                            <pre>
&lt;!-- justify center tabs --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap justify-center mt-3 border-b border-white-light dark:border-[#191e3a]&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Home&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Profile&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Contact&lt;/a
            &gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Justify Center Pills -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Justify Center Pills</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code14')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap justify-center mt-3 space-x-2 rtl:space-x-reverse">
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Home</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Profile</a
                                ></Tab
                            >
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Contact</a
                                ></Tab
                            >
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code14')">
                        <highlight>
                            <pre>
&lt;!-- justify center pills --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap justify-center mt-3 space-x-2 rtl:space-x-reverse&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Home&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Profile&lt;/a
            &gt;&lt;/Tab
        &gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Contact&lt;/a
            &gt;&lt;/Tab
        &gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Justify Right Tabs -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Justify Right Tabs</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code15')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap justify-end mt-3 border-b border-white-light dark:border-[#191e3a]">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Home</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Profile</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300"
                                    :class="{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }"
                                    >Contact</a
                                >
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel class="active">
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code15')">
                        <highlight>
                            <pre>
&lt;!-- justify right tabs --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap justify-end mt-3 border-b border-white-light dark:border-[#191e3a]&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Home&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Profile&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block border border-transparent hover:border-white-light hover:border-b-white dark:hover:border-[#191e3a] dark:hover:border-b-black !outline-none transition duration-300&quot;
                :class=&quot;{ 'text-primary !border-white-light !border-b-white dark:!border-[#191e3a] dark:!border-b-black': selected }&quot;
                &gt;Contact&lt;/a
            &gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
        &lt;TabPanel class=&quot;active&quot;&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Justify Right pills -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Justify Right Pills</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code16')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap justify-end mt-3 space-x-2 rtl:space-x-reverse">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Home</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Profile</a
                                >
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300"
                                    :class="{ 'bg-info text-white': selected }"
                                    >Contact</a
                                >
                            </Tab>
                        </TabList>
                        <TabPanels class="pt-5 flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code16')">
                        <highlight>
                            <pre>
&lt;!-- justify right pills --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap justify-end mt-3 space-x-2 rtl:space-x-reverse&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Home&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Profile&lt;/a
            &gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 -mb-[1px] block hover:bg-info rounded hover:text-white !outline-none transition duration-300&quot;
                :class=&quot;{ 'bg-info text-white': selected }&quot;
                &gt;Contact&lt;/a
            &gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;pt-5 flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Pills with Icon -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Pills with Icon</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code17')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="grid grid-cols-4 gap-2 sm:flex sm:flex-wrap sm:justify-center mt-3 mb-5 sm:space-x-3 rtl:space-x-reverse">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] !outline-none transition duration-300"
                                    :class="{ '!bg-success text-white': selected }"
                                >
                                    <icon-home class="mb-1" />

                                    Home
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] !outline-none transition duration-300"
                                    :class="{ '!bg-success text-white': selected }"
                                >
                                    <icon-user class="w-5 h-5 mb-1" />
                                    Profile
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] !outline-none transition duration-300"
                                    :class="{ '!bg-success text-white': selected }"
                                >
                                    <icon-phone class="mb-1" />
                                    Contact
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] !outline-none transition duration-300"
                                    :class="{ '!bg-success text-white': selected }"
                                >
                                    <icon-settings class="w-5 h-5 mb-1" />
                                    Settings
                                </a>
                            </Tab>
                        </TabList>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <blockquote
                                    class="text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]"
                                >
                                    <div class="flex items-start">
                                        <p class="not-italic text-[#515365] text-sm dark:text-white-dark m-0">
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                                        </p>
                                    </div>
                                </blockquote>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code17')">
                        <highlight>
                            <pre>
&lt;!-- pills with icon --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;grid grid-cols-4 gap-2 sm:flex sm:flex-wrap sm:justify-center mt-3 mb-5 sm:space-x-3 rtl:space-x-reverse&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] !outline-none transition duration-300&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Home
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] !outline-none transition duration-300&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Profile
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] !outline-none transition duration-300&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Contact
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] !outline-none transition duration-300&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
                Settings
            &lt;/a&gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;blockquote
                class=&quot;text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]&quot;
            &gt;
                &lt;div class=&quot;flex items-start&quot;&gt;
                    &lt;p class=&quot;not-italic text-[#515365] text-sm dark:text-white-dark m-0&quot;&gt;
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/blockquote&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Rounded Pills with Icon -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Rounded Pills with Icon</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code18')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5">
                        <TabList class="flex flex-wrap justify-center mt-3 mb-5 space-x-3 rtl:space-x-reverse">
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                    :class="{ '!bg-info text-white': selected }"
                                >
                                    <icon-home class="w-6 h-6" />
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                    :class="{ '!bg-info text-white': selected }"
                                >
                                    <icon-user class="w-6 h-6" />
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                    :class="{ '!bg-info text-white': selected }"
                                >
                                    <icon-phone class="w-6 h-6" />
                                </a>
                            </Tab>
                            <Tab as="template" v-slot="{ selected }">
                                <a
                                    href="javascript:;"
                                    class="w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                    :class="{ '!bg-info text-white': selected }"
                                >
                                    <icon-settings />
                                </a>
                            </Tab>
                        </TabList>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <blockquote
                                    class="text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]"
                                >
                                    <div class="flex items-start">
                                        <p class="not-italic text-[#515365] text-sm dark:text-white-dark m-0">
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                                        </p>
                                    </div>
                                </blockquote>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code18')">
                        <highlight>
                            <pre>
&lt;!-- rounded pills with icon --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5&quot;&gt;
    &lt;TabList class=&quot;flex flex-wrap justify-center mt-3 mb-5 space-x-3 rtl:space-x-reverse&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-info text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-info text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-info text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
            &lt;/a&gt;
        &lt;/Tab&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
            &lt;a
                href=&quot;javascript:;&quot;
                class=&quot;w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-info text-white': selected }&quot;
            &gt;
                &lt;svg&gt; ... &lt;/svg&gt;
            &lt;/a&gt;
        &lt;/Tab&gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;blockquote
                class=&quot;text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]&quot;
            &gt;
                &lt;div class=&quot;flex items-start&quot;&gt;
                    &lt;p class=&quot;not-italic text-[#515365] text-sm dark:text-white-dark m-0&quot;&gt;
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/blockquote&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Vertical Rounded With Icon -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Vertical Rounded With Icon</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code19')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5 flex flex-col sm:flex-row">
                        <div class="mx-10 mb-5 sm:mb-0">
                            <TabList class="flex flex-col justify-center m-auto space-y-3 w-24">
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                        :class="{ '!bg-success text-white': selected }"
                                    >
                                        <icon-home class="mb-1" />
                                        Home
                                    </a>
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                        :class="{ '!bg-success text-white': selected }"
                                    >
                                        <icon-user class="w-5 h-5 mb-1" />
                                        Profile
                                    </a>
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                        :class="{ '!bg-success text-white': selected }"
                                    >
                                        <icon-phone class="mb-1" />
                                        Contact
                                    </a>
                                </Tab>
                            </TabList>
                        </div>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code19')">
                        <highlight>
                            <pre>
&lt;!-- vertical rounded with icon --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5 flex flex-col sm:flex-row&quot;&gt;
    &lt;div class=&quot;mx-10 mb-5 sm:mb-0&quot;&gt;
        &lt;TabList class=&quot;flex flex-col justify-center m-auto space-y-3 w-24&quot;&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                    :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;
                    &lt;svg&gt; ... &lt;/svg&gt;
                    Home
                &lt;/a&gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                    :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;
                    &lt;svg&gt; ... &lt;/svg&gt;
                    Profile
                &lt;/a&gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;p-7 py-3 flex flex-col items-center justify-center rounded-lg bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-success hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                    :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;
                    &lt;svg&gt; ... &lt;/svg&gt;
                    Contact
                &lt;/a&gt;
            &lt;/Tab&gt;
        &lt;/TabList&gt;
    &lt;/div&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Vertical Circle With Icon -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Vertical Circle With Icon</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code20')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5 flex flex-col sm:flex-row">
                        <div class="mx-10 mb-5 sm:mb-0">
                            <TabList class="flex flex-col justify-center items-center space-y-3">
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                        :class="{ '!bg-info text-white': selected }"
                                    >
                                        <icon-home class="w-6 h-6" />
                                    </a>
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                        :class="{ '!bg-info text-white': selected }"
                                    >
                                        <icon-user class="w-6 h-6" />
                                    </a>
                                </Tab>
                                <Tab as="template" v-slot="{ selected }">
                                    <a
                                        href="javascript:;"
                                        class="w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none"
                                        :class="{ '!bg-info text-white': selected }"
                                    >
                                        <icon-phone class="w-6 h-6" />
                                    </a>
                                </Tab>
                            </TabList>
                        </div>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code20')">
                        <highlight>
                            <pre>
&lt;!-- vertical circle dith icon --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5 flex flex-col sm:flex-row&quot;&gt;
    &lt;div class=&quot;mx-10 mb-5 sm:mb-0&quot;&gt;
        &lt;TabList class=&quot;flex flex-col justify-center items-center space-y-3&quot;&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                    :class=&quot;{ '!bg-info text-white': selected }&quot;
                &gt;
                    &lt;svg&gt; ... &lt;/svg&gt;
                &lt;/a&gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                    :class=&quot;{ '!bg-info text-white': selected }&quot;
                &gt;
                    &lt;svg&gt; ... &lt;/svg&gt;
                &lt;/a&gt;
            &lt;/Tab&gt;
            &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;&gt;
                &lt;a
                    href=&quot;javascript:;&quot;
                    class=&quot;w-16 h-16 flex flex-col items-center justify-center rounded-full bg-[#f1f2f3] dark:bg-[#191e3a] hover:!bg-info hover:text-white hover:shadow-[0_5px_15px_0_rgba(0,0,0,0.30)] transition-all duration-300 !outline-none&quot;
                    :class=&quot;{ '!bg-info text-white': selected }&quot;
                &gt;
                    &lt;svg&gt; ... &lt;/svg&gt;
                &lt;/a&gt;
            &lt;/Tab&gt;
        &lt;/TabList&gt;
    &lt;/div&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Vertical Pills -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Vertical Pills</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code21')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5 flex flex-col sm:flex-row">
                        <TabList class="ltr:pr-4 rtl:pl-4 space-y-2 sm:flex-[0_0_20%] mb-5 sm:mb-0">
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none"
                                    :class="{ '!bg-success text-white': selected }"
                                    >Home</a
                                ></Tab
                            >
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none"
                                    :class="{ '!bg-success text-white': selected }"
                                    >Profile</a
                                ></Tab
                            >
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none"
                                    :class="{ '!bg-success text-white': selected }"
                                    >Messages</a
                                ></Tab
                            >
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none"
                                    :class="{ '!bg-success text-white': selected }"
                                    >Settings</a
                                ></Tab
                            >
                        </TabList>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <blockquote
                                    class="text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]"
                                >
                                    <div class="flex items-start">
                                        <p class="not-italic text-[#515365] text-sm dark:text-white-dark m-0">
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                                        </p>
                                    </div>
                                </blockquote>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code21')">
                        <highlight>
                            <pre>
&lt;!-- vertical pills --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5 flex flex-col sm:flex-row&quot;&gt;
    &lt;TabList class=&quot;ltr:pr-4 rtl:pl-4 space-y-2 sm:flex-[0_0_20%] mb-5 sm:mb-0&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;Home&lt;/a
            &gt;&lt;/Tab
        &gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;Profile&lt;/a
            &gt;&lt;/Tab
        &gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;Messages&lt;/a
            &gt;&lt;/Tab
        &gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;Settings&lt;/a
            &gt;&lt;/Tab
        &gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;blockquote
                class=&quot;text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]&quot;
            &gt;
                &lt;div class=&quot;flex items-start&quot;&gt;
                    &lt;p class=&quot;not-italic text-[#515365] text-sm dark:text-white-dark m-0&quot;&gt;
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/blockquote&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>

                <!-- Justify Vertical Pills Right -->
                <div class="panel">
                    <div class="flex items-center justify-between mb-5">
                        <h5 class="font-semibold text-lg dark:text-white-light">Justify Vertical Pills Right</h5>
                        <a
                            class="font-semibold hover:text-gray-400 dark:text-gray-400 dark:hover:text-gray-600"
                            href="javascript:;"
                            @click="toggleCode('code22')"
                        >
                            <span class="flex items-center">
                                <icon-code class="me-2" />
                                Code
                            </span>
                        </a>
                    </div>
                    <TabGroup as="div" class="mb-5 flex flex-col sm:flex-row sm:gap-4">
                        <TabList class="space-y-2 sm:flex-[0_0_20%] mb-5 sm:mb-0 sm:order-1">
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none"
                                    :class="{ '!bg-success text-white': selected }"
                                    >Home</a
                                ></Tab
                            >
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none"
                                    :class="{ '!bg-success text-white': selected }"
                                    >Profile</a
                                ></Tab
                            >
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none"
                                    :class="{ '!bg-success text-white': selected }"
                                    >Messages</a
                                ></Tab
                            >
                            <Tab as="template" v-slot="{ selected }"
                                ><a
                                    href="javascript:;"
                                    class="p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none"
                                    :class="{ '!bg-success text-white': selected }"
                                    >Settings</a
                                ></Tab
                            >
                        </TabList>
                        <TabPanels class="flex-1 text-sm">
                            <TabPanel>
                                <h4 class="font-semibold text-2xl mb-4">We move your world!</h4>
                                <p class="mb-4">
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <div class="flex items-start">
                                    <div class="w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none">
                                        <img
                                            src="/assets/images/profile-34.jpeg"
                                            alt=""
                                            class="w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover"
                                        />
                                    </div>
                                    <div class="flex-auto">
                                        <h5 class="text-xl font-medium mb-4">Media heading</h5>
                                        <p class="text-white-dark">
                                            Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio,
                                            vestibulum in vulputate at, tempus viverra turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia
                                            congue felis in faucibus.
                                        </p>
                                    </div>
                                </div>
                            </TabPanel>
                            <TabPanel>
                                <p>
                                    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                                    dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
                                    proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </TabPanel>
                            <TabPanel>
                                <blockquote
                                    class="text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]"
                                >
                                    <div class="flex items-start">
                                        <p class="not-italic text-[#515365] text-sm dark:text-white-dark m-0">
                                            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                                        </p>
                                    </div>
                                </blockquote>
                            </TabPanel>
                        </TabPanels>
                    </TabGroup>
                    <template v-if="codeArr.includes('code22')">
                        <highlight>
                            <pre>
&lt;!-- justify vertical pills right --&gt;
&lt;TabGroup as=&quot;div&quot; class=&quot;mb-5 flex flex-col sm:flex-row&quot;&gt;
    &lt;TabList class=&quot;ltr:pr-4 rtl:pl-4 space-y-2 sm:flex-[0_0_20%] mb-5 sm:mb-0 sm:order-1&quot;&gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;Home&lt;/a
            &gt;&lt;/Tab
        &gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;Profile&lt;/a
            &gt;&lt;/Tab
        &gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;Messages&lt;/a
            &gt;&lt;/Tab
        &gt;
        &lt;Tab as=&quot;template&quot; v-slot=&quot;{ selected }&quot;
            &gt;&lt;a
                href=&quot;javascript:;&quot;
                class=&quot;p-3.5 py-2 block rounded-md hover:bg-success hover:text-white transition-all duration-300 !outline-none&quot;
                :class=&quot;{ '!bg-success text-white': selected }&quot;
                &gt;Settings&lt;/a
            &gt;&lt;/Tab
        &gt;
    &lt;/TabList&gt;
    &lt;TabPanels class=&quot;flex-1 text-sm&quot;&gt;
        &lt;TabPanel&gt;
            &lt;h4 class=&quot;font-semibold text-2xl mb-4&quot;&gt;We move your world!&lt;/h4&gt;
            &lt;p class=&quot;mb-4&quot;&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;div class=&quot;flex items-start&quot;&gt;
                &lt;div class=&quot;w-20 h-20 ltr:mr-4 rtl:ml-4 flex-none&quot;&gt;
                    &lt;img src=&quot;/assets/images/profile-34.jpeg&quot; alt=&quot;&quot; class=&quot;w-20 h-20 m-0 rounded-full ring-2 ring-[#ebedf2] dark:ring-white-dark object-cover&quot; /&gt;
                &lt;/div&gt;
                &lt;div class=&quot;flex-auto&quot;&gt;
                    &lt;h5 class=&quot;text-xl font-medium mb-4&quot;&gt;Media heading&lt;/h5&gt;
                    &lt;p class=&quot;text-white-dark&quot;&gt;
                        Cras sit amet nibh libero, in gravida nulla. Nulla vel metus scelerisque ante sollicitudin. Cras purus odio, vestibulum in vulputate at, tempus viverra
                        turpis. Fusce condimentum nunc ac nisi vulputate fringilla. Donec lacinia congue felis in faucibus.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/div&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;p&gt;
                Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
                exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
                pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
            &lt;/p&gt;
        &lt;/TabPanel&gt;
        &lt;TabPanel&gt;
            &lt;blockquote
                class=&quot;text-black p-5 ltr:pl-3.5 rtl:pr-3.5 bg-white shadow-md rounded-tr-md rounded-br-md border border-white-light border-l-2 !border-l-primary dark:bg-[#060818] dark:border-[#060818]&quot;
            &gt;
                &lt;div class=&quot;flex items-start&quot;&gt;
                    &lt;p class=&quot;not-italic text-[#515365] text-sm dark:text-white-dark m-0&quot;&gt;
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis
                        nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
                    &lt;/p&gt;
                &lt;/div&gt;
            &lt;/blockquote&gt;
        &lt;/TabPanel&gt;
    &lt;/TabPanels&gt;
&lt;/TabGroup&gt;

&lt;!-- script --&gt;
&lt;script lang=&quot;ts&quot; setup&gt;
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
&lt;/script&gt;
</pre
                            >
                        </highlight>
                    </template>
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts" setup>
    import highlight from '@/components/plugins/highlight.vue';
    import codePreview from '@/composables/codePreview';
    import { TabGroup, TabList, Tab, TabPanels, TabPanel } from '@headlessui/vue';
    import { useMeta } from '@/composables/use-meta';

    import IconBell from '@/components/icon/icon-bell.vue';
    import IconCode from '@/components/icon/icon-code.vue';
    import IconHome from '@/components/icon/icon-home.vue';
    import IconUser from '@/components/icon/icon-user.vue';
    import IconPhone from '@/components/icon/icon-phone.vue';
    import IconInfoCircle from '@/components/icon/icon-info-circle.vue';
    import IconSettings from '@/components/icon/icon-settings.vue';

    useMeta({ title: 'Tabs' });
    const { codeArr, toggleCode } = codePreview();
</script>
